---

# Micro:bit Guide

---

## Objective

The goal of this program is to:

- **Detect a loud sound** → When the micro:bit hears a noise, it triggers the music playback.

- **Play the melody** → Using music blocks, the micro:bit plays a sequence of notes.

- **Loop twice** → The melody repeats twice before stopping.

![SingingChiikawaCompleted11](./images/image-20250416-084747.png)
![SingingChiikawaCompleted12](./images/image-20250416-084849(1).png)

## Step-by-Step Guide

**Step 1: Initialise the Music System**

- Activate the built-in speaker

 - Use set built-in speaker to on to ensure the micro:bit can produce sound.

- Adjust the volume

  - set volume to 255 to make sure the audio is loud and clear.

**Step 2: Detect Sound**

- Use the "On Loud Sound" Event

 - When the micro:bit detects a loud noise (such as a clap or knock), the program initiates.

 - This is managed using on loud sound detected.

**Step 3: Play the Melody Twice**

- Use a Loop for Repetition

 - A repeat 2 times block ensures the melody plays twice before stopping.

- Define the Melody

 - Example note sequence:

    play note G for 1 beat

    pause 500 milliseconds

    play note E for 1 beat

    play note A for 1/2 beat

    play note G for 1/2 beat

    pause 500 milliseconds

    play note F for 1/2 beat

    play note F for 1/2 beat

## Principles and Logic Behind the Code

**Event-Triggered Execution**

- Using on loud sound detected, we ensure that the program only runs when sound is detected instead of looping indefinitely.

**Controlled Repetition**

- The repeat 2 times loop guarantees that the melody plays exactly twice before stopping, maintaining a predictable behaviour.

**Timing and Musical Flow**

- Notes are structured with different durations (1 beat, 1/2 beat), making the melody sound natural.

- Pauses (500 milliseconds) add spacing to improve rhythm.

By following these steps, your micro:bit will successfully respond to sound, play a melody twice, and then stop!