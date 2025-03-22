# Module 4: Advanced Git Topics

## Lesson 3: Working with Stashed Changes

Imagine you're in the middle of working on a new feature, you've made several changes but haven't committed them yet. Suddenly, you realize there's an urgent bug on the `main` branch that needs immediate attention. You don't want to commit your half-finished feature, but you also need to switch branches. This is where **Git Stash** comes to the rescue! Think of it as a way to temporarily put your current work aside on a shelf so you can quickly handle something else.

## What is Git Stash?

Git Stash allows you to temporarily save your modified tracked files and staged changes (and optionally, even untracked files) without committing them. It essentially takes the dirty state of your working directory – your modified tracked files and staged changes – and saves it on a stack of stashes. This lets you switch branches, pull in updates, or do other work, and then easily come back and reapply your stashed changes later.

## Why Use Git Stash?

Git Stash is incredibly useful in several scenarios:

- **Switching Context Quickly:** You can switch to a different branch to work on a high-priority task without having to commit your current, incomplete work.
- **Keeping Branches Clean:** It helps keep your feature branches or other work branches focused on completed, committed work before you switch to a different context.
- **Avoiding Accidental Commits:** It prevents you from making premature or messy commits just so you can switch branches.

## Basic Usage of `git stash`

Let's look at the fundamental `git stash` commands:

- **Stashing Your Work:** To save your uncommitted changes, simply run:

  ```bash
  git stash
  ```

  Git will save your changes and revert your working directory back to the state of your last commit on the current branch. You'll see output similar to:

  ```
  Saved working directory and index state WIP on your-branch: a1b2c3d Your last commit message
  ```

  "WIP" stands for "Work In Progress."

- **Listing Stashes:** To see a list of all the stashes you've saved, use:

  ```bash
  git stash list
  ```

  The output will show your stashes, usually with an index (like `stash@{0}`), the branch they were created on, and the description (which is often the commit message of the commit you were on when you stashed):

  ```
  stash@{0}: WIP on your-branch: a1b2c3d Your last commit message
  stash@{1}: WIP on main: e5f6g7h Another commit message
  ```

  The most recent stash is at the top (`stash@{0}`).

- **Applying a Stash:** To bring your stashed changes back, you can use `git stash apply` followed by the name of the stash you want to apply. If you don't specify a stash name, it defaults to the most recent one (`stash@{0}`):

  ```bash
  git stash apply stash@{0}
  # OR simply:
  git stash apply
  ```

  This will attempt to reapply the changes to your current branch. If there are no conflicts, your working directory will be updated with the stashed changes. The stash will remain in the list, in case you want to apply it to other branches or later.

- **Applying and Removing a Stash:** If you're sure you want to apply a stash and don't need it anymore, you can use `git stash pop`. This command applies the stash and then immediately removes it from the stash list:
  ```bash
  git stash pop stash@{0}
  # OR simply:
  git stash pop
  ```

## Stashing Untracked Files

By default, `git stash` only saves changes to tracked files (those that have been added to Git). If you have new, untracked files that you also want to stash, you can use the `-u` or `--include-untracked` option:

```bash
git stash -u
# OR
git stash --include-untracked
```

## Stashing with a Message

To make it easier to remember what a particular stash was for, you can add a descriptive message when you create it using `git stash save` followed by your message in quotes:

```bash
git stash save "WIP: Implementing user authentication"
```

Now, when you run `git stash list`, you'll see your message:

```
stash@{0}: WIP on your-branch: a1b2c3d Your last commit message
stash@{1}: WIP: Implementing user authentication
```

## Viewing Stash Details

If you want to see the specific changes that are stored in a stash without actually applying it, you can use `git stash show -p` followed by the stash name:

```bash
git stash show -p stash@{1}
```

This will display a diff of the changes in that stash.

## Creating a Branch from a Stash

Sometimes, you might stash some changes and then realize you want to continue working on them in a new branch. Git allows you to create a new branch directly from a stash using `git stash branch` followed by the new branch name and the stash name:

```bash
git stash branch feature-authentication stash@{1}
```

This command will create a new branch named `feature-authentication` at the commit where you created the stash, and it will apply the changes from `stash@{1}` to this new branch. The stash will also be removed from your stash list.

## Clearing Stashes

If you have stashes that you no longer need, you can remove them:

- **Removing a Specific Stash:** To remove a specific stash, use `git stash drop` followed by the stash name:

  ```bash
  git stash drop stash@{0}
  ```

- **Removing All Stashes:** To remove all stashes in your stash list, use:
  ```bash
  git stash clear
  ```
  **Be careful when using this command, as it will permanently delete all your saved stashes!**

## Example Scenario

Let's walk through a common scenario:

1.  You are working on a feature in a branch called `feature-x`. You've made some changes but haven't committed them yet.
2.  Suddenly, a critical bug is reported on the `main` branch. You need to switch to `main` immediately to fix it.
3.  You don't want to commit your unfinished work on `feature-x`, so you stash it:
    ```bash
    git stash save "WIP: Feature X implementation"
    ```
4.  You switch to the `main` branch:
    ```bash
    git checkout main
    ```
5.  You fix the bug on the `main` branch, commit your changes, and push them:
    ```bash
    # Fix the bug
    git add .
    git commit -m "Fix: Critical bug on main"
    git push origin main
    ```
6.  Now, you want to go back to working on your feature. You switch back to your `feature-x` branch:
    ```bash
    git checkout feature-x
    ```
7.  You can now reapply your stashed changes:
    ```bash
    git stash pop
    ```
    Your work on feature X is now back in your working directory, and the stash has been removed from the list.

## Analogy Revisited

Think of your Git repository as your desk. When you're working on a task (your current branch), you might have some papers and tools scattered around (your uncommitted changes). If you suddenly need to work on a different task (switch to another branch), you can use Git Stash to neatly stack those papers and tools (your uncommitted changes) and place them on a temporary shelf (the stash list). When you're ready to go back to the original task, you can easily take the stack back down and continue where you left off.

## Conclusion

Git Stash is a powerful tool for managing uncommitted changes, allowing you to switch contexts quickly and keep your branches clean. By understanding how to stash, list, apply, and manage your stashes, you can significantly improve your Git workflow and handle interruptions with ease.

## Next Steps

Now that we've learned about Git Stash, let's explore how to apply specific commits from one branch to another using **Git Cherry-pick** in the next lesson. This can be useful when you need to bring over a particular change without merging the entire branch.

```

```
