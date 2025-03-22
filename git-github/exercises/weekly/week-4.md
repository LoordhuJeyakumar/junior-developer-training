# Weekly Exercises - Week 4: Advanced Merging and Automation

**Objective:** Explore advanced merge options and get introduced to Git Hooks.

**Scenario:** You need to integrate a specific bug fix from the `main` branch into your `feature-refactor` branch, and you want to start automating some checks in your repository.

**Prerequisites:** You should have your `task-manager` repository with a `main` branch and a `feature-refactor` branch (or any other feature branch).

**Tasks:**

1.  **Cherry-picking a Bug Fix:**

    - Imagine there was a critical bug fixed on your `main` branch in a commit with a specific hash.
    - Switch to your `feature-refactor` branch.
    - Use `git cherry-pick <commit_hash_of_bug_fix_on_main>` to apply that specific bug fix to your `feature-refactor` branch.

2.  **Advanced Merging:**

    - Create a new branch named `feature-ui-updates` from your `main` branch.
    - Make some significant UI changes in this branch and commit them.
    - Switch back to your `main` branch and make some other changes in the same files that might conflict with the UI updates. Commit these changes.
    - Now, merge the `feature-ui-updates` branch into `main` using the `--no-commit` option.
    - Inspect the merge result, stage any resolved conflicts, and then create a custom merge commit message.
    - Try the same merge again but this time use the `-X ours` or `-X theirs` option to see how Git automatically handles conflicts (be cautious with this and understand the implications).

3.  **Introduction to Git Hooks:**
    - Navigate to the `.git/hooks` directory in your local `task-manager` repository.
    - Find the `pre-commit.sample` file and make a copy of it named `pre-commit` (without the `.sample` extension).
    - Open the `pre-commit` script in a text editor. Uncomment a simple check (e.g., the one that checks for trailing whitespace) and save the file.
    - Make a change to one of your project files and add trailing whitespace at the end of a line.
    - Try to commit this change. You should see that the `pre-commit` hook prevents the commit due to the trailing whitespace.
    - Remove the trailing whitespace and try committing again. The commit should now succeed.

**Review:** This week, you should have gained experience with selectively applying changes using cherry-pick, exploring advanced merge options to control the merge process, and getting a basic introduction to automating tasks with Git Hooks.
