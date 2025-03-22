# Lesson 3: Basic Git Workflow

Now that we have Git installed and configured, let's dive into the basic workflow of using Git to track changes in your projects. This lesson will cover the core commands you'll use regularly.

## Creating a Local Repository (`git init`)

The first step in using Git for a new project is to initialize a Git repository. This is done using the `git init` command.

- **What it does:** `git init` creates a new, empty Git repository in the current directory. It adds a hidden `.git` subdirectory that contains all the necessary repository metadata.
- **How to use it:**
  1.  Open your terminal or command prompt.
  2.  Navigate to the root directory of your project using the `cd` command.
  3.  Run the command: `git init`
- **Example:**
  ```bash
  cd my-new-project
  git init
  Initialized empty Git repository in /path/to/my-new-project/.git/
  ```
- **What happens:** After running this command, your project directory is now under Git's control.

## Staging Changes (`git add`)

Once you've made changes to your files (created new files, modified existing ones, or deleted files), Git needs to know which of these changes you want to include in your next snapshot (commit). This is where the staging area comes in, and the `git add` command is used to add changes to this area.

- **What it does:** `git add` adds changes from your working directory to the staging area. The staging area is like a preparation area for your next commit.
- **How to use it:**
  - **Add a specific file:** `git add <filename>` (e.g., `git add index.html`)
  - **Add multiple specific files:** `git add <filename1> <filename2> ...`
  - **Add all changes in the current directory and its subdirectories:** `git add .` (Use with caution, make sure you're not adding unwanted files!)
- **Example:**
  ```bash
  # After modifying index.html and style.css
  git add index.html
  git add style.css
  ```

## Committing Changes (`git commit`)

After you've staged your changes using `git add`, the next step is to save these changes permanently in the Git history. This is done using the `git commit` command.

- **What it does:** `git commit` takes the changes that are staged in the staging area and saves them as a new snapshot in your repository's history. You must include a commit message that briefly describes the changes you've made.
- **How to use it:**
  - **Basic commit with a message:** `git commit -m "Your commit message here"`
  - **Open an editor to write a more detailed commit message:** `git commit` (without the `-m` flag) will open your configured text editor.
- **Example:**
  ```bash
  git commit -m "Added initial HTML structure and basic styling"
  [master (root-commit) a1b2c3d] Added initial HTML structure and basic styling
   2 files changed, 15 insertions(+)
   create mode 100644 index.html
   create mode 100644 style.css
  ```
- **Importance of Commit Messages:** Writing clear and concise commit messages is crucial. They help you and other collaborators understand the history of changes in the project. Good commit messages should answer the question: "What and why was this change made?"

## Checking the Status (`git status`)

At any point, you can use the `git status` command to see the current state of your working directory and the staging area.

- **What it does:** `git status` shows you:
  - Which files have been modified but not yet staged.
  - Which files are staged and ready to be committed.
  - Which files are being tracked by Git and are up-to-date.
  - Any new files that Git hasn't started tracking yet.
- **How to use it:** Simply run the command: `git status`
- **Example:**

  ```bash
  # After modifying a file but not staging it
  git status
  On branch master
  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   script.js

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          new_feature.js

  no changes added to commit (use "git add" and/or "git commit -a")
  ```

## Viewing Commit History (`git log`)

The `git log` command allows you to view the history of commits in your repository.

- **What it does:** `git log` displays a list of commits, showing information like the commit author, date, time, and the commit message.
- **How to use it:** Simply run the command: `git log`
- **Example:**

  ```bash
  git log
  commit a1b2c3d4e5f67890abcdef1234567890abcdef (HEAD -> master)
  Author: Your Name <your.email@example.com>
  Date:   Tue Mar 21 15:30:00 2023 +0000

      Added initial HTML structure and basic styling

  commit 0987654321fedcba0987654321fedcba0987
  Author: Another Developer <another.dev@example.com>
  Date:   Mon Mar 20 10:00:00 2023 +0000

      Initial project setup
  ```

- **Useful `git log` Options:**
  - `git log --oneline`: Displays each commit on a single line, showing only the commit hash and the commit message.
  - `git log --author="Your Name"`: Shows commits only by a specific author.
  - `git log --since="yesterday"` or `git log --until="last week"`: Filters commits by date.
  - `git log -n 5`: Shows the last 5 commits.

## Getting Help with Git Commands (`git help`)

Git has excellent built-in documentation, and the `git help` command is your best friend when you're unsure about how a command works or what options it has.

- **What it does:** `git help <command>` opens the manual page for the specified Git command in your terminal.
- **How to use it:** Simply type `git help` followed by the command you want to learn more about.
- **Examples:**
  - `git help init`: Opens the manual page for the `git init` command.
  - `git help add`: Opens the manual page for the `git add` command.
  - `git help commit`: Opens the manual page for the `git commit` command.
  - `git help status`: Opens the manual page for the `git status` command.
  - `git help log`: Opens the manual page for the `git log` command.
- **Alternative Ways to Get Help:** You can also use the `--help` option with most Git commands:
  - `git init --help`
  - `git add --help`
  - `git commit --help`
  - `git status --help`
  - `git log --help`
  - And you can also use `-h` as a shorthand: `git init -h`

**How to Navigate the Help Page:**

When you run `git help <command>`, a manual page will open in your terminal (often using a program like `less`). You can typically navigate this page using the following keys:

- **`j` or Down Arrow:** Scroll down one line.
- **`k` or Up Arrow:** Scroll up one line.
- **Spacebar:** Scroll down one page.
- **`b`:** Scroll up one page.
- **`/` followed by a term and Enter:** Search for a specific term within the manual page.
- **`q`:** Quit the help page and return to the command prompt.

**Why is `git help` Important?**

As you learn more about Git, you'll encounter many commands and options. The `git help` command is your go-to resource for understanding how to use them correctly. It provides detailed explanations of what each command does, its available options, and examples of its usage. Encourage your junior developers to use `git help` whenever they are unsure about a command.

## A Simple Basic Workflow Example

Let's put these commands together in a simple scenario:

1.  **Start a new project:**
    ```bash
    mkdir my-website
    cd my-website
    git init
    ```
2.  **Create an `index.html` file and add some basic content.**
3.  **Stage the `index.html` file:**
    ```bash
    git add index.html
    ```
4.  **Commit the changes:**
    ```bash
    git commit -m "Initial commit: Added basic HTML"
    ```
5.  **Make some changes to `index.html` (e.g., add a heading).**
6.  **Check the status:**
    ```bash
    git status
    ```
    You'll see that `index.html` is modified but not staged.
7.  **Stage the changes again:**
    ```bash
    git add index.html
    ```
8.  **Commit the updated changes:**
    ```bash
    git commit -m "Updated index.html with a heading"
    ```
9.  **View the commit history:**
    ```bash
    git log --oneline
    ```
    You should see two commits listed.

## Conclusion

In this lesson, we covered the fundamental commands for the basic Git workflow: `git init`, `git add`, `git commit`, `git status`, `git log`, and `git help`. These are the commands you'll use most frequently when working with Git to track changes in your projects.

## Next Steps

In the next lesson, we will learn about how to ignore specific files and directories using the `.gitignore` file. This is important for keeping your repository clean and preventing unnecessary files from being tracked.
