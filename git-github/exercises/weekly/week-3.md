# Weekly Exercises - Week 3: Mastering Commit History and Recovery

**Objective:** Practice advanced Git techniques for managing commit history and recovering from mistakes.

**Scenario:** You've been working on a feature branch for your `task-manager` application and your local history has become a bit messy. You also need to recover from an accidental deletion.

**Prerequisites:** You should have a local `task-manager` repository with a few feature branches and some commits on them.

**Tasks:**

1.  **Interactive Rebase for Cleanup:**

    - Create a new branch named `feature-refactor`.
    - Make at least 5-6 small commits on this branch, some with very short or unclear messages (e.g., "fix", "more work", "oops").
    - Use `git rebase -i HEAD~6` to interactively rebase these commits.
    - For some commits, use the `reword` command to make the messages clearer.
    - Use the `squash` command to combine a few related commits into one logical commit.
    - If there's a commit you no longer need, use the `drop` command to remove it.
    - Push your cleaned-up branch to GitHub (you might need to use `git push --force-with-lease` if you've already pushed this branch).

2.  **Recovering from a Mistake with Reflog:**

    - On your `main` branch, accidentally perform a hard reset to the previous commit using `git reset --hard HEAD^`.
    - Realize your mistake and use `git reflog` to find the commit you accidentally removed.
    - Use `git checkout` with the reflog entry to go back to that commit.
    - Create a new branch from this point to preserve the recovered work.

3.  **Stashing Workflow:**
    - Switch to your `feature-refactor` branch (or any other branch where you have ongoing work).
    - Start making some changes to a file but don't commit them.
    - You suddenly need to switch to the `main` branch to fix a critical bug. Use `git stash` to save your current changes.
    - Switch to the `main` branch, fix the bug, commit the fix, and push it to GitHub.
    - Switch back to your `feature-refactor` branch and use `git stash pop` to reapply your stashed work.

**Review:** This week's exercises should make you more comfortable with manipulating your commit history using interactive rebase, recovering from accidental actions with `git reflog`, and effectively managing interruptions in your workflow with `git stash`.
