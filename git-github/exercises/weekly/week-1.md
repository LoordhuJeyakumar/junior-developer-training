# Weekly Exercises - Week 1: Foundations of Git

**Objective:** Integrate the knowledge gained from Modules 1 and 2.

**Scenario:** You are starting a new personal project - a simple task management application.

**Tasks:**

1.  **Initialize Repository:** Create a new directory named `task-manager` and initialize a Git repository inside it.
2.  **Basic Structure:** Create the following files: `index.html`, `style.css`, `script.js`, and `README.md`. Add some basic content to each file to represent the initial structure of your application.
3.  **Initial Commit:** Stage all the files and make an initial commit with a descriptive message.
4.  **Feature Branch: User Authentication:**
    - Create a new branch named `feature-auth`.
    - In this branch, add code to `index.html` and `script.js` to implement a basic login form. You don't need to make it fully functional, just the UI elements.
    - Add and commit these changes with a message like "Implemented basic login form UI".
5.  **Feature Branch: Task List:**
    - Switch back to the `main` branch.
    - Create another new branch named `feature-tasks`.
    - In this branch, add HTML to `index.html` to display a list of tasks. Add some placeholder tasks.
    - Add and commit these changes with a message like "Added basic task list UI".
6.  **Merge and Resolve Conflicts:**
    - Switch back to the `main` branch.
    - Merge the `feature-auth` branch into `main`.
    - Now, merge the `feature-tasks` branch into `main`. If there are any merge conflicts (likely in `index.html`), resolve them carefully, stage the resolved file, and complete the merge.
7.  **Ignoring Files:**
    - Imagine your project now has a `node_modules` directory (if you were using Node.js). Create a dummy `node_modules` directory.
    - Create a `.gitignore` file and add `node_modules/` to it.
    - Verify that Git is now ignoring this directory.

**Review:** By the end of this week, you should be comfortable with initializing repositories, tracking files, making commits, creating and merging branches, and resolving basic merge conflicts.
