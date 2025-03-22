**Welcome to the Junior Developer Training Program!**

This guide will walk you through how to use the learning materials in this repository and how to submit your work for review.

**I. Utilizing the Study Material**

This training program is structured to help you learn essential skills for becoming a junior developer. The materials are organized by topic, with each topic having its own dedicated folder:

- `git-github/`: Contains modules and lessons for learning Git and GitHub.
- `javascript/`: Contains modules and lessons for learning JavaScript (will be added later).
- `react/`: Contains modules and lessons for learning React (will be added later).

**Navigating the Repository:**

1.  **Choose a Topic:** Start with the `git-github/` folder. The other topics will be covered later.
2.  **Explore Modules:** Within each topic folder, you will find modules that group related lessons. For example, in `git-github/`, you'll find `module-1`, `module-2`, `module-3`, and `module-4`.
3.  **Follow Lessons:** Each module contains individual lesson files (usually in Markdown format, e.g., `lesson-1-what-is-version-control.md`). Open these files to read the content for each lesson.
4.  **Code Examples:** Pay close attention to the code examples provided in the lessons. Try typing these examples out and running them on your own computer to understand how they work.
5.  **Hands-on Exercises:** To reinforce your learning, complete the exercises located in the `exercises/` directory. You'll find subdirectories for `daily` and `weekly` exercises, often organized by module. Follow the instructions in each exercise file.
6.  **Practical Projects:** At the end of certain modules or weeks, you might find practical projects. These projects will require you to apply the skills you've learned to build something more substantial. Follow the project descriptions carefully.

**Tips for Effective Learning:**

- **Go in Order:** It's recommended to go through the modules and lessons in the order they are presented, as they often build upon each other.
- **Be Active:** Don't just read the material passively. Actively try out the Git commands, write code, and experiment with the concepts.
- **Take Notes:** Feel free to take notes as you go through the material. This can help you remember key concepts and commands.
- **Ask Questions:** If you get stuck or have questions, don't hesitate to ask your instructor for help. You can use GitHub Issues in this repository to ask questions related to specific lessons or exercises.

**II. Submitting Your Work for Review (Using GitHub Pull Requests)**

To submit your completed tasks, exercises, or projects for review, please follow these steps:

1.  **Fork the Repository:**

    - Go to the GitHub page of the main training program repository (e.g., `your-github-username/junior-developer-training`).
    - Click the "Fork" button in the top right corner. This will create a copy of the repository in your own GitHub account.

2.  **Clone Your Fork:**

    - On your GitHub account, go to your forked repository.
    - Click the "Code" button and copy the repository URL (either HTTPS or SSH).
    - Open your terminal or command prompt on your local machine.
    - Navigate to the directory where you want to store your training files.
    - Run the command: `git clone <your_forked_repository_url>` (replace `<your_forked_repository_url>` with the URL you copied).

3.  **Create a Branch for Your Submission:**

    - Navigate into your cloned repository directory: `cd junior-developer-training` (or whatever the repository name is).
    - Create a new branch for the specific task or exercise you are submitting. Use a clear and descriptive name, for example:
      - For Module 1 Daily Exercises: `exercises/daily/module-1-submission`
      - For the Week 1 Weekly Exercise: `exercises/weekly/week-1-submission`
      - For the Task Manager Project: `projects/task-manager-submission`
      - Use the command: `git checkout -b <your_branch_name>` (replace `<your_branch_name>` with your chosen name).

4.  **Complete Your Work:**

    - Perform the tasks, complete the exercises, or finish your project on this branch. Make sure to save your changes to the relevant files.

5.  **Stage and Commit Your Changes:**

    - Use `git add .` to stage all your changes.
    - Use `git commit -m "Your descriptive commit message"` to commit your changes. Write a clear message explaining what you have done. Make multiple commits if necessary to logically group your work.

6.  **Push Your Branch to Your Fork:**

    - Push your local branch to your forked repository on GitHub: `git push origin <your_branch_name>` (replace `<your_branch_name>` with the name of your branch).

7.  **Create a Pull Request:**
    - Go to your forked repository on GitHub in your web browser.
    - You should see a notification that you recently pushed a branch and an option to "Compare & pull request". Click this button.
    - Alternatively, you can go to the "Pull requests" tab in your forked repository and click "New pull request".
    - **Important:** On the "Compare" page:
      - Ensure the **base repository** is the main training repository (`your-github-username/junior-developer-training`).
      - The **base** should be the submission branch your instructor has specified (e.g., `submissions` or `main`). If no specific branch is mentioned, default to the `main` branch of the main repository.
      - Your **head repository** should be your fork.
      - The **compare** branch should be the branch you just pushed (`exercises/daily/module-1-submission`, `exercises/weekly/week-1-submission`, `projects/task-manager-submission`, etc.).
    - Add a clear and informative **title** to your Pull Request (e.g., "Submission for Module 1 Daily Exercises").
    - In the **description**, provide details about the work you have done, any challenges you encountered, and any specific feedback you would like from the instructor.
    - Click the "Create pull request" button.

Your submission will now be visible to your instructor for review. They will provide feedback directly on your Pull Request. Make sure to check your Pull Request for any comments or requests for changes.

---
