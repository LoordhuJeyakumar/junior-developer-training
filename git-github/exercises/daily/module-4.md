# Daily Exercises - Module 4: Advanced Git Topics

**Objective:** Get hands-on experience with advanced Git features.

**Instructions:** Continue working in a local Git repository with a few commits and branches.

1.  **Interactive Rebase Practice:**

    - Create a new branch and make at least three small commits on it, some with minor typos in the messages.
    - Use `git rebase -i HEAD~3` to interactively rebase these commits.
    - Use the `reword` command to fix the commit message typos.
    - Use the `squash` command to combine two of the commits into one.

2.  **Reflog Recovery:**

    - Create a new branch and make a commit on it.
    - Switch back to your main branch and accidentally delete the new branch using `git branch -D <branch_name>`.
    - Use `git reflog` to find the commit hash of the last commit on the deleted branch.
    - Create a new branch from that commit hash to recover your work.

3.  **Stashing Changes:**

    - Start making changes to a file in your working directory but don't commit them.
    - Use `git stash` to temporarily save these changes.
    - Switch to another branch, make some changes and commit them.
    - Switch back to your original branch and use `git stash pop` to reapply your stashed changes.

4.  **Cherry-picking:**
    - Create a new branch and make a commit with a specific change.
    - Switch back to your main branch.
    - Use `git cherry-pick` to apply the commit from the other branch to your main branch.

**Review:** Practice these advanced Git commands to become more comfortable with history manipulation, error recovery, and workflow management.
