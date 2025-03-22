# Git and GitHub Training for Junior Developers

**Welcome to the Comprehensive Git and GitHub Training Module!**

This module is an integral part of the Junior Developer Training Program, meticulously crafted to equip you with the essential skills for mastering Git, a powerful distributed version control system, and GitHub, the leading platform for collaborative software development. Proficiency in these tools is indispensable for any aspiring software developer, enabling you to efficiently manage code changes, collaborate seamlessly with team members, and contribute effectively to projects of any scale.

## Module Overview

This training module is thoughtfully structured into four key modules, each building upon the knowledge gained in the previous one. By the successful completion of this module, you will be empowered to:

- Grasp the fundamental concepts of version control and articulate its critical importance in modern software development.
- Install, configure, and personalize your Git environment on your local machine.
- Execute core Git operations, including initializing repositories, staging and committing changes, and inspecting repository status and history.
- Leverage the power of branching to isolate features, manage parallel development efforts, and maintain code stability.
- Merge branches effectively and skillfully resolve any conflicts that may arise during the integration of changes.
- Comprehend the architecture and functionalities of GitHub as a platform for hosting Git repositories and fostering collaborative workflows.
- Create and manage your own Git repositories on GitHub, setting the stage for personal projects and team collaboration.
- Establish a robust connection between your local Git repositories and their remote counterparts on GitHub, facilitating seamless synchronization.
- Collaborate effectively with fellow developers using GitHub's intuitive features, such as Issues for tracking tasks and Pull Requests for code review and contribution.
- Gain an understanding of fundamental branching strategies employed in team-based software development to ensure organized and efficient collaboration.

## Prerequisites

Before embarking on this learning journey, it is recommended that you possess:

- **Basic Computer Literacy:** A foundational understanding of computer operations, including file system navigation and the use of a text editor.
- **Command Line Basics (Highly Recommended):** While the initial lessons might not heavily rely on it, a basic familiarity with the command line or terminal will significantly enhance your learning experience, especially as we delve into more advanced Git operations.

## Learning Objectives

Upon successful completion of this module, you will be able to:

- **Explain the Core Concepts:** Articulate the principles of version control, its advantages in software development, and the role of Git and GitHub.
- **Set Up Your Environment:** Install and configure Git on your local development machine, including basic settings and personalization.
- **Master Basic Git Operations:**
    - Initialize a new Git repository for a project using `git init`.
    - Track changes to files by adding them to the staging area (`git add`) and committing them to the repository (`git commit`).
    - Check the current status of your repository using `git status`.
    - Review the history of changes using `git log`.
- **Utilize `.gitignore`:** Effectively use `.gitignore` files to specify intentionally untracked files that Git should ignore.
- **Work with Branches:**
    - Create new branches using `git branch` and `git checkout`.
    - Switch between different branches to manage concurrent development.
    - Merge changes from one branch into another using `git merge`.
    - Identify and resolve merge conflicts that occur during the merging process.
    - Delete branches that are no longer needed using `git branch -d` or `git branch -D`.
- **Engage with Remote Repositories on GitHub:**
    - Create and manage repositories on GitHub through its web interface.
    - Establish a connection between a local Git repository and a remote repository on GitHub using `git remote add`.
    - Push local commits to a remote GitHub repository using `git push`.
    - Retrieve changes from a remote GitHub repository using `git pull` and `git fetch`.
- **Collaborate Using GitHub Features:**
    - Utilize GitHub Issues to track tasks, report bugs, and facilitate discussions around specific aspects of the project.
    - Understand the Pull Request workflow on GitHub for proposing code changes, conducting code reviews, and integrating contributions.
    - Identify and resolve merge conflicts that arise within Pull Requests on GitHub.
- **Understand Branching Strategies:** Gain a foundational understanding of common branching strategies like Gitflow and feature branch workflows used in collaborative software development environments.
- **Explore Advanced Git Topics:**
    - Clean up commit history using interactive rebasing (`git rebase -i`).
    - Recover from mistakes using `git reflog`.
    - Temporarily save uncommitted changes using `git stash`.
    - Apply specific commits from one branch to another using `git cherry-pick`.
    - Utilize advanced merge options to handle complex scenarios.
    - Manage project dependencies using Git Submodules.
    - Automate tasks within your Git workflow using Git Hooks.

## How to Use This Material

This training module is thoughtfully structured into sequential lessons. It is highly recommended to progress through the lessons in the order they are presented, as each lesson builds upon the concepts introduced in the previous ones. Each lesson typically includes:

- **Clear Explanations:** Concise and easy-to-understand explanations of the core concepts.
- **Practical Code Examples:** Real-world examples of Git commands and their practical application in development scenarios.
- **Hands-on Exercises:** Engaging tasks and activities designed to reinforce your understanding and provide practical experience with Git and GitHub. **(Note: Refer to the `exercises/` directory for these.)**
- **Real-World Scenarios:** Illustrative examples of how these concepts are applied in actual software development workflows and team collaborations.

It is crucial to actively participate in the hands-on exercises and experiment with the Git commands yourself. This active engagement is key to truly internalizing the concepts and developing a strong practical understanding of Git and GitHub.

## Module Breakdown

**Module 1: Introduction to Version Control and Git**

- [Lesson 1: What is Version Control?](./git-github/module-1/lesson-1-what-is-version-control.md) - Understanding the core concepts and benefits of version control systems.
- [Lesson 2: Installing and Setting Up Git](./git-github/module-1/lesson-2-installing-git.md) - A step-by-step guide to installing Git on your local machine and performing initial configuration.
- [Lesson 3: Basic Git Workflow](./git-github/module-1/lesson-3-basic-workflow.md) - Learning the fundamental Git commands for tracking changes: `init`, `add`, `commit`, `status`, `log`.
- [Lesson 4: Ignoring Files with `.gitignore`](./git-github/module-1/lesson-4-gitignore.md) - Understanding how to create and utilize `.gitignore` files to exclude specific files and directories from version control.

**Module 2: Working with Branches**

- [Lesson 1: Understanding Branches](./git-github/module-2/lesson-1-understanding-branches.md) - Exploring the concept of branching in Git and its importance in managing different lines of development.
- [Lesson 2: Creating and Switching Branches](./git-github/module-2/lesson-2-merging-branches.md) - Learning how to create new branches using `git branch` and switch between them using `git checkout`.
- [Lesson 3: Merging Branches](./git-github/module-2/lesson-3-merge-conflicts.md) - Mastering the process of integrating changes from one branch into another using `git merge`.
- [Lesson 4: Exploring Changes with Git Diff](./git-github/module-2/lesson-4-exploring-changes-with-git-diff.md) - Understanding how to use `git diff` to inspect changes between commits, branches, and your working directory.
- [Lesson 5: Undoing Changes with Git Reset](./git-github/module-2/lesson-5-undoing-changes-with-git-reset.md) - Learning different ways to undo changes in your Git repository using `git reset`.
- [Lesson 6: Managing Files](./git-github/module-2/lesson-6-managing-files.md) - Understanding how to move, rename, and remove files under Git's control.
- [Lesson 7: Revisiting Git Checkout](./git-github/module-2/lesson-7-revisiting-git-checkout.md) - Exploring the various uses of `git checkout`, including switching branches and checking out specific commits or files.

**Module 3: Remote Repositories and GitHub**

- [Lesson 1: Introduction to Remote Repositories](./git-github/module-3/lesson-1-introduction-to-remote-repositories.md) - Understanding the concept of remote repositories and their role in collaboration.
- [Lesson 2: Setting Up a Remote Repository on GitHub](./git-github/module-3/lesson-2-pushing-to-a-remote-repository.md) - A step-by-step guide to creating a new repository on GitHub.
- [Lesson 3: Connecting Local Repository to GitHub](./git-github/module-3/lesson-3-pulling-from-a-remote-repository.md) - Learning how to link your local Git repository with a remote repository on GitHub using `git remote add`.
- [Lesson 4: Pushing, Pulling, and Fetching](./git-github/module-3/lesson-4-fetching-and-cloning-remote-repositories.md) - Mastering the commands for synchronizing changes between local and remote repositories: `git push`, `git pull`, and `git fetch`.
- [Lesson 5: Collaborating with Branches and Pull Requests on GitHub](./git-github/module-3/lesson-5-collaborating-with-branches-and-pull-requests.md) - Understanding and participating in collaborative workflows using branches and Pull Requests on GitHub.
- [Lesson 6: Working with GitHub Issues](./git-github/module-3/lesson-6-working-with-gitHub-issues.md) - Utilizing GitHub Issues for task management, bug reporting, and project discussions.
- [Lesson 7: Exploring Forks and Contributing to Open Source](./git-github/module-3/lesson-7-exploring-forks-and-contributing-to-open-source.md) - Understanding how to fork repositories and contribute to open-source projects on GitHub.

**Module 4: Advanced Git Topics**

- [Lesson 1: Cleaning Up History with Interactive Rebasing](./git-github/module-4/lesson-1-cleaning-up-history-with-interactive-rebasing.md) - Learning how to use `git rebase -i` to edit, reorder, squash, and drop commits in your history.
- [Lesson 2: Recovering from Mistakes with Git Reflog](./git-github/module-4/lesson-2-recovering-from-mistakes-with-git-reflog.md) - Utilizing `git reflog` to track changes to HEAD and recover lost commits.
- [Lesson 3: Working with Stashed Changes](./git-github/module-4/lesson-3-working-with-stashed-changes.md) - Learning how to use `git stash` to temporarily save uncommitted changes.
- [Lesson 4: Applying Specific Changes with Cherry-picking](./git-github/module-4/lesson-4-applying-specific-changes-with-cherry-picking.md) - Understanding how to apply specific commits from one branch to another using `git cherry-pick`.
- [Lesson 5: Exploring Advanced Merge Options](./git-github/module-4/lesson-5-exploring-advanced-merge-options.md) - Discovering and utilizing advanced options with the `git merge` command.
- [Lesson 6: Managing Dependencies with Git Submodules](./git-github/module-4/lesson-6-managing-dependencies-with-git-submodules.md) - Learning how to manage external dependencies as separate Git repositories using submodules.
- [Lesson 7: Automating Tasks with Git Hooks](./git-github/module-4/lesson-7-automating-tasks-with-git-hooks.md) - Understanding and using Git Hooks to automate tasks within your workflow.

## Practical Real-World Scenario

- [Project: Collaborative Website Development](./project-collaborative-website.md) - Engage in a hands-on project where you will collaboratively build a simple website using the Git and GitHub skills you've acquired throughout this module. This project will simulate a real-world development environment. **(Note: The content for this project will be provided separately.)**

## Exercises

- [Daily Exercises](./exercises/daily/) - Short, focused exercises designed to reinforce the concepts learned in each day's lessons. **(Note: The content for these exercises will be provided separately.)**
- [Weekly Exercises](./exercises/weekly/) - More comprehensive exercises that challenge you to apply the knowledge gained over a week to solve more complex problems. **(Note: The content for these exercises will be provided separately.)**

## Getting Started

1.  **Install Git:** Ensure that Git is installed on your local machine. If you haven't already done so, please refer to [Lesson 2: Installing and Setting Up Git](./git-github/module-1/lesson-2-installing-git.md) for detailed instructions.
2.  **Create a GitHub Account:** If you don't have one, sign up for a free account at [https://github.com/](https://github.com/).
3.  **Navigate to the Training Directory:** Open your terminal or command prompt and navigate to the root directory of this training program.
4.  **Initialize Git (If Necessary):** If you haven't already, initialize a Git repository in the root directory by running `git init`.
5.  **Begin with Module 1:** Start your learning journey with **Module 1: Introduction to Version Control and Git** and follow the lessons in the order they are presented. Click on the lesson links in the "Module Breakdown" section above to access the content.

## Contributing

We encourage you to contribute to the improvement of this learning material. If you have any suggestions for enhancements, find any errors, or believe certain topics could be explained more clearly, please don't hesitate to create an issue or submit a pull request to this repository. Your feedback is valuable in making this resource better for future junior developers.

## License

This training material is provided under the **MIT License**, a free and open-source license that allows for broad use and modification.

---