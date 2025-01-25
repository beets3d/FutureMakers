---
title: Setup Opensource tool chain for coursekit
marp: true
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

# **Tool Chain Introduction**

## [1. Git introduction](#git-introduction)

## [2. Github introduction](#github-introduction)

## [3. VSCode / Cursor](#vscode)

## [4. Markdown](#markdown)

## [5. Warp for VSCode](#warp-for-vscode)

## [6. Github pages](#github-pages)
---

# **Git Introduction**
<style scoped>
li {
    font-size: 24px;
}
</style>
- What is Git?
  1. Git is a free and open-source source control management (SCM) system.
  2. It is a distributed version control system for tracking changes in source code.
  3. Git's primary function is to track changes to files over time, allowing users to revert to previous versions and compare differences.

- Why Use Git?
  1. Manage changes to files: Git allows you to see who changed what and compare different versions.
  2. Revert to previous versions: If you make a mistake, you can jump back to a previous version.
  3. Experiment safely: Use branches to work on new features or fixes without affecting the main code.
  4. Track project history: Git keeps a record of all changes made, creating a project history.

---

- Key Git Concepts
  1. Repository (Repo): A storage location for source code, documentation, and other files with all its history. Represented by the hidden .git folder.
  2. Commit: A snapshot of a repository at a specific point in time, creating a record of changes made.
  3. Branch: A parallel version of a project's code, allowing developers to work on features or fixes without affecting the main code.
  4. Staging: A transitional area where changes are prepared to be included in the next commit.
  5. Working Directory: The area where you make edits to your files.

---

# **Git commands**

- git clone: Clone a repository from a remote source.

```
git clone https://github.com/beets3d/FutureMakers.git
```

---

# **Github Introduction**
<style scoped>
li {
    font-size: 25px;
}
</style>
- What is GitHub? Test change test change
  1. GitHub is a web-based platform for version control and collaboration using Git.
  2. It provides cloud hosting for Git repositories.
  3. It offers tools for project management, issue tracking, and code review.

- Key GitHub Features
  1. Remote Repositories: GitHub hosts repositories that can be accessed by multiple users.
  2. Collaboration: GitHub facilitates collaboration through features like issues, pull requests, and project management tools.
  3. Issues: Used to track feature requests, bug reports, or questions related to a project.
  4. Pull Requests: A request to merge changes from one branch into another, often used in collaborative workflows.

---
<style scoped>
li {
    font-size: 25px;
}
</style>
- Connecting Local Git to GitHub
  1. Create a Repository on GitHub: Set up a new repository on GitHub.
  2. Add Remote: Connect your local repo to a remote GitHub repo with the command git remote add origin <github_repo_URL>.
  3. Set Main Branch: Set the target branch to main using git branch -M main.
  4. Push to GitHub: Push your local repo to the remote with the command git push -u origin main. git push --all will push all branches to GitHub.

- Working with GitHub
  1. Making Changes: Edit files directly on GitHub or make changes locally and push them.
  2. Downloading Changes: Use git fetch to download all the remote history or git pull to download all remote history and merge it with local files.
  3. Collaboration: Use issues and pull requests to manage changes and collaborate with others.
  4. Releases: Create releases to mark specific versions of your project.
---

# **VSCode / Cursor**

- VSCode
    1. VSCode is a code editor developed by Microsoft. It is a powerful and versatile tool that supports multiple programming languages and has a wide range of extensions for enhancing productivity.
    2. Download VSCode from [here](https://code.visualstudio.com/)
- Cursor
    1. Cursor is an AI-powered code editor developed by Cursor AI. It uses AI to assist with code writing, debugging, and refactoring. Cursor integrates with GitHub, allowing for seamless collaboration and version control.
    2. Download Cursor from [here](https://www.cursor.com/)
---

# **Markdown**
<style scoped>
table {
    font-size: 16px;
}
</style>
- Markdown is a lightweight markup language with plain text formatting syntax. It is designed to be easy to read, write, and format.
- Markdown syntax: [https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)
- Examples:

    | Syntax                  | Example                                      |
    |-------------------------|----------------------------------------------|
    | `# Heading`             | # Heading                                    |
    | `**bold text**`         | **bold text**                                |
    | `*italic text*`         | *italic text*                                |
    | `[Link](URL)`           | [Link](https://example.com)                  |
    | `` `code` ``            | `code`                                       |
    | `![Beets Logo](https://beets3d.github.io/FutureMakers/assets/beets-logo-square.avif)` | <img src="https://beets3d.github.io/FutureMakers/assets/beets-logo-square.avif" alt="Beets Logo" width="60"/>|

---

# **Warp for VSCode / Cursor**

- Marpit /mɑːrpɪt/ is the skinny framework for creating slide deck from Markdown. It can transform Markdown and CSS theme(s) to slide deck composed of static HTML and CSS and create a web page convertible into slide PDF by printing.
- We can use Marpit in VSCode or Cursor to create slide deck from Markdown with a excellent editing experience. It also helps us to generate slides from Markdown in our own website.
- Install Marpit in VSCode or Cursor: [https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

---

# **Github pages**

- Github pages is a static website hosting service that allows us to host our own website for free.
- We can use Github pages to host our own website.

# **This is Edward test**

- this is first point test
- this is cursor test
- [Visit YouTube](https://www.youtube.com)
<style>
table {
    border-collapse: collapse;
    width: 100%;
    margin: 20px 0;
}

th {
    background-color: #4CAF50;
    color: white;
    padding: 12px;
    text-align: left;
}

td {
    padding: 8px;
    border: 1px solid #ddd;
}

tr:nth-child(even) {
    background-color: #f2f2f2;
}

tr:hover {
    background-color: #ddd;
}
</style>

| 1/one | two   | three | four  |
|-------|--------|--------|--------|
| 2     | test1  | edited | -      |
| 3     | -      | -      | -      |
| 4     | -      | -      | -      |
| 5     | -      | -      | -      |
| 6     | -      | -      | -      |
| 7     | -      | -      | -      |
| 8     | -      | -      | -      |
| 9     | -      | -      | -      |
| 10    | [Go to Tags](tags.en.md){ .md-button } | -      | -      |
[Go to Index](index.md){ .md-button }






