---
title: Pi Setup Guide
lang_name: en 
comments: true

---

# Pi Setup Guide

---

# Step-by-Step Guide to Create a Continuous Physical Chatbot on Raspberry Pi 5

## Overview
This guide will help you create a physical chatbot using your Raspberry Pi 5 with 8GB RAM, supporting continuous conversation in Cantonese and English. The system will include:
- Continuous speech-to-text conversion using Whisper
- Natural Language Processing with DeepSeek R1 1.5B on Ollama
- Streaming text-to-speech using espeak-ng for both Cantonese and English
- Language detection for each interaction
- Immediate acknowledgment after recording
- A main application to coordinate the workflow
- Automatic startup after reboot

## Step 1: Set Up Your Raspberry Pi

1. Install Raspberry Pi OS (formerly Raspbian) on your Raspberry Pi 5
2. Connect necessary hardware:
   - Microphone for audio input
   - Speakers for audio output
3. Update your system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
## Step 2: Install System Dependencies

1. Install Ollama for running DeepSeek models:
   ```bash
   curl -fsSL https://ollama.com/install.sh | sh

   ollama run humblemat/hon9kon9ize_CantoneseLLMChat-v1.0-7B-F16.gguf.q8_0
   ```

2. Install audio utilities:
   ```bash
   sudo apt install espeak-ng alsa-utils
   sudo apt-get install portaudio19-dev
   ```
## Step 3: Create Project Folder and Virtual Environment

1. Create a project folder and navigate into it:
   ```bash
   mkdir ~/pi-chatbot
   cd ~/pi-chatbot
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv chatbot-venv
   source chatbot-venv/bin/activate
   ```

## Step 4: Install Required Packages

Create a file named `requirements.txt` with the following content:
```
openai-whisper
pyaudio
numpy
requests
pyttsx3
ollama
transformers
```

Install the requirements:
```bash
pip install -r requirements.txt
```



## Step 5: Create Project Files

Create the following files in your project directory:

### 1. main.py - The Main Application with Continuous Conversation
```python
import os
import subprocess
import time
import pyaudio
import wave
import whisper

from stt import transcribe_audio
from nlp import generate_response
from streaming_tts import StreamingTextToSpeech

def record_audio(audio_file, duration=5):
    CHUNK = 1024
    FORMAT = pyaudio.paInt16
    CHANNELS = 1
    RATE = 16000

    p = pyaudio.PyAudio()

    stream = p.open(
        format=FORMAT,
        channels=CHANNELS,
        rate=RATE,
        input=True,
        frames_per_buffer=CHUNK
    )

    print("Recording...")
    frames = []

    for _ in range(0, int(RATE / CHUNK * duration)):
        data = stream.read(CHUNK)
        frames.append(data)

    print("Finished recording")

    stream.stop_stream()
    stream.close()
    p.terminate()

    wf = wave.open(audio_file, 'wb')
    wf.setnchannels(CHANNELS)
    wf.setsampwidth(p.get_sample_size(FORMAT))
    wf.setframerate(RATE)
    wf.writeframes(b''.join(frames))
    wf.close()

def main():
    while True:
        print("Chatbot activated. Speak now...")
        
        # Initialize streaming text-to-speech with default language (English)
        # We'll change language later if needed
        tts = StreamingTextToSpeech("en")
        
        # Inform user we're listening
        tts.speak_immediate("I'm listening")
        
        # Record full audio
        audio_file = "input.wav"
        record_audio(audio_file)
        
        # Transcribe audio to text with language detection
        text, language = transcribe_audio(audio_file)
        print(f"User said: {text}")
        
        # If language changed, re-initialize TTS with detected language
        if language != "en":
            tts = StreamingTextToSpeech(language)
            if language == "zh-yue":
                tts.speak_immediate("我正在聽")
            else:
                tts.speak_immediate("I'm listening")
        
        # Play immediate acknowledgment
        if language == "zh-yue":
            tts.speak_immediate("好的，請稍候")
        else:
            tts.speak_immediate("ok got it")
        
        # Generate response using NLP model with streaming
        print("Generating response...")
        response_stream = generate_response(text)
        
        # Stream the response and speak incrementally
        response_text = ""
        for chunk in response_stream:
            print(chunk, end="", flush=True)
            response_text += chunk
            tts.speak(chunk)
        
        # Ensure any remaining audio is played
        tts.finalize()
        
        # Check if user wants to continue
        if "no" in text.lower() or "bye" in text.lower() or "再見" in text:
            tts.speak_immediate("Goodbye!")
            break
        else:
            tts.speak_immediate("Is there anything else I can help?")

if __name__ == "__main__":
    main()
```

### 2. stt.py - Speech-to-Text with Whisper (tiny model) and Language Detection
```python
import whisper

def transcribe_audio(audio_file):
    model = whisper.load_model("tiny")  # Using tiny model for faster speed
    result = model.transcribe(audio_file, fp16=False)  # Add fp16=False to avoid CPU warning
    
    # Detect language
    language = result["language"]
    
    # Map language code to espeak-ng voice
    if language == "zh":
        language = "zh-yue"
    else:
        language = "en"
    
    return result["text"], language
```

### 3. nlp.py - NLP Processing with Ollama
```python
import sys
import json
from ollama import chat

def generate_response(prompt):
    stream = chat(
        model="deepseek-r1:1.5b",
        messages=[{"role": "user", "content": prompt}],
        stream=True
    )
    
    for chunk in stream:
        yield chunk["content"]
```

### 4. streaming_tts.py - Streaming Text-to-Speech with espeak-ng
```python
import subprocess
import tempfile
import os
import re
import shlex
import time

class StreamingTextToSpeech:
    def __init__(self, language="en"):
        self.language = language
        self.temp_dir = tempfile.mkdtemp()
        self.audio_files = []
        self.current_audio = None
        self.process = None
        self.buffer = ""
        self.word_pause = 0.05  # Reduced pause between words
        self.speech_rate = 150  # Increased speech rate
        # Sentence boundary characters for both English and Chinese
        self.sentence_boundary = [".", "!", "?", ";", ":", "。", "！", "？", "；", "："]
        self.max_buffer_length = 20  # Maximum words to buffer before forcing a speak

    def speak(self, text):
        self.buffer += text
        # Check if we have a complete sentence
        if any(self.buffer.endswith(char) for char in self.sentence_boundary):
            self._process_text(self.buffer)
            self.buffer = ""
        # If buffer exceeds max length without a sentence boundary, process anyway
        elif len(self.buffer.split()) >= self.max_buffer_length:
            self._process_text(self.buffer)
            self.buffer = ""

    def _process_text(self, text):
        # Create temporary audio file
        audio_file = os.path.join(self.temp_dir, f"temp_{len(self.audio_files)}.wav")
        self.audio_files.append(audio_file)
        
        # Generate speech for the text chunk
        if self.language == "zh-yue":
            command = f"espeak-ng -v zh-yue -p 70 -s {self.speech_rate} -a 120 {shlex.quote(text)} -w {shlex.quote(audio_file)}"
        else:
            command = f"espeak-ng -v en-us -p 70 -s {self.speech_rate} -a 120 {shlex.quote(text)} -w {shlex.quote(audio_file)}"
        
        subprocess.call(command, shell=True)
        
        # Play the audio immediately
        if self.process is not None and self.process.poll() is None:
            self.process.terminate()
        
        self.process = subprocess.Popen(["aplay", audio_file])
        # Wait for the audio to finish playing
        while self.process.poll() is None:
            time.sleep(0.1)
        # Add a small pause between words
        time.sleep(self.word_pause)

    def speak_immediate(self, text):
        # Create temporary audio file
        audio_file = os.path.join(self.temp_dir, f"immediate_{len(self.audio_files)}.wav")
        self.audio_files.append(audio_file)
        
        # Generate speech for the complete text
        if self.language == "zh-yue":
            command = f"espeak-ng -v zh-yue -p 70 -s {self.speech_rate} -a 120 {shlex.quote(text)} -w {shlex.quote(audio_file)}"
        else:
            command = f"espeak-ng -v en-us -p 70 -s {self.speech_rate} -a 120 {shlex.quote(text)} -w {shlex.quote(audio_file)}"
        
        subprocess.call(command, shell=True)
        
        # Wait for the audio file to be created
        max_wait = 5  # Maximum wait time in seconds
        wait_time = 0
        while not os.path.exists(audio_file) and wait_time < max_wait:
            time.sleep(0.1)
            wait_time += 0.1
        
        if not os.path.exists(audio_file):
            print(f"Error: Audio file {audio_file} was not created within {max_wait} seconds")
            return
        
        # Play the audio immediately and wait for it to finish
        play_command = ["aplay", audio_file]
        try:
            subprocess.run(play_command, check=True)
        except subprocess.CalledProcessError as e:
            print(f"Error playing audio: {e}")
        
        # Remove the temporary file if it exists
        if os.path.exists(audio_file):
            os.remove(audio_file)

    def finalize(self):
        # Process any remaining text in buffer
        if self.buffer:
            self._process_text(self.buffer)
            self.buffer = ""
        
        # Wait for any remaining audio to finish
        if self.process is not None:
            self.process.wait()
        
        # Clean up temporary files
        for audio_file in self.audio_files:
            if os.path.exists(audio_file):
                os.remove(audio_file)
        if os.path.exists(self.temp_dir):
            os.rmdir(self.temp_dir)
```

## Step 6: Set Up Automatic Startup

To ensure your chatbot works even after Raspberry Pi is restarted, create a systemd service:

1. Create a service file:
   ```bash
   sudo nano /etc/systemd/system/chatbot.service
   ```

2. Add the following content, using absolute paths:
   ```
   [Unit]
   Description=Chatbot Service
   After=network.target

   [Service]
   ExecStart=/home/pi/pi-chat-bot/chatbot-venv/bin/python3 /home/pi/pi-chat-bot/main.py
   WorkingDirectory=/home/pi/pi-chat-bot
   Restart=always
   User=pi

   [Install]
   WantedBy=multi-user.target
   ```

3. Enable and start the service:
   ```bash
   sudo systemctl enable chatbot.service
   sudo systemctl start chatbot.service
   ```

4. Check the service status:
   ```bash
   sudo systemctl status chatbot.service
   ```

## Step 7: Run the Complete System

1. Start the Ollama server:
   ```bash
   ollama serve
   ```

2. The chatbot should now automatically start when your Raspberry Pi boots up. You can also manually run it by activating the virtual environment and executing:
   ```bash
   source ~/pi-chat-bot/chatbot-venv/bin/activate
   python3 ~/pi-chat-bot/main.py
   ```

3. Speak your query when prompted

## Customization Options

1. Adjust audio recording parameters in main.py
2. Modify espeak-ng parameters in streaming_tts.py for different voices
3. Experiment with different Whisper models in stt.py
4. Try different DeepSeek models in nlp.py

## Troubleshooting

- If you encounter audio issues, check your ALSA configuration
- Ensure your microphone and speakers are properly connected
- Verify Ollama is running before starting the application
- Check the service logs if the chatbot doesn't start automatically:
  ```bash
  journalctl -u chatbot.service -e
  ```

This setup provides a foundation for your physical chatbot with Cantonese and English support. You can extend it by adding more features like:
- Custom voice training
- Additional NLP models
- GUI interface
- Integration with other IoT devices