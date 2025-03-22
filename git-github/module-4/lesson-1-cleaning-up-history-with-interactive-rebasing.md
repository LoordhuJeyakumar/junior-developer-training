# Module 4: Advanced Git Topics

## Lesson 1: Cleaning Up History with Interactive Rebasing

As you work on projects, especially in feature branches, your local commit history might become a bit messy. You might have commits with very short or unclear messages, or perhaps you made several small commits that could be combined into a single, more meaningful one. **Interactive rebasing** is a powerful Git tool that allows you to edit, reorder, squash, and even drop commits in your history before sharing them with others.

## Understanding Rebasing (A Quick Recap)

Before we dive into interactive rebasing, let's briefly recall what regular rebasing does. When you rebase a branch onto another (e.g., `git rebase main`), you are essentially moving the base of your current branch to the tip of the target branch. This results in a linear commit history, as if your changes were made directly on top of the target branch.

## What is Interactive Rebasing?

Interactive rebasing takes this concept a step further. When you initiate an interactive rebase, Git opens an editor (usually your default text editor) where you can see a list of the commits in the range you've specified. You can then tell Git how you want to modify these commits using various commands.

## When to Use Interactive Rebasing

Interactive rebasing is particularly useful in the following scenarios:

- **Cleaning Up Feature Branches:** Before merging a feature branch into the main branch, you can use interactive rebase to squash multiple small commits into a few logical ones, rewrite commit messages for clarity, or remove unnecessary commits.
- **Amending Older Commits:** If you realize you made a mistake in an earlier commit that hasn't been pushed yet, you can use interactive rebase to go back and amend it.
- **Reordering Commits:** If the order of your commits doesn't logically flow, you can rearrange them using interactive rebase.

**Important Caution:** Avoid using interactive rebase on commits that have already been pushed to a shared remote repository. Rewriting history on shared branches can cause significant problems for your collaborators. It's generally safe to use interactive rebase on local branches that haven't been shared yet.

## Initiating an Interactive Rebase

To start an interactive rebase, you use the `git rebase -i` command followed by a reference to the commit you want to rebase onto. This reference can be a branch name (like `main`) or a specific commit hash.

For example, if you are on a feature branch and you want to interactively rebase all commits made since you branched off the `main` branch, you would run:

```bash
git rebase -i main
```

Alternatively, if you want to modify the last `n` commits, you can use `HEAD~n`. For example, to edit the last 3 commits:

```bash
git rebase -i HEAD~3
```

## The Interactive Rebase Editor

When you run the interactive rebase command, Git will open your configured text editor with a list of your commits. Each commit will be listed with a command at the beginning. Here's an example of what you might see:

```
pick a1b2c3d Commit message one
pick e5f6g7h Commit message two
pick i8j9k0l Commit message three

# Rebase 0123456..i8j9k0l onto 0123456 (3 commands)
#
# Commands:
#  p, pick <commit> = use commit
#  r, reword <commit> = use commit, but edit the commit message
#  e, edit <commit> = use commit, but stop for amending
#  s, squash <commit> = use commit, but meld into the previous commit
#  f, fixup <commit> = like "squash", but discard this commit's log message
#  d, drop <commit> = remove commit
#  l, label <label> = label current HEAD
#  t, reset <label> = reset HEAD to label
#  m, merge [-C <commit> | --allow-empty] <label> # create a merge commit
#  T, exec <command> = run command (the whole line) and stop if it fails
#  b, break = stop here (continue rebase later with --continue)
#  S, stop = stop here
#
# These lines can be reordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
```

This editor shows your commits in reverse chronological order (the oldest commit is at the top). You can now modify the commands next to each commit to tell Git what you want to do.

## Common Interactive Rebase Commands

Here are some of the most commonly used commands:

- **`pick` (or `p`)**: This is the default command. It means you want to keep the commit as is.
- **`reword` (or `r`)**: You want to keep the commit but change its commit message. Git will open another editor for you to rewrite the message.
- **`edit` (or `e`)**: You want to keep the commit but stop the rebase at this point so you can make further changes to the files in this commit (using `git amend --no-edit` to keep the message or `git commit --amend` to change it). After making changes, you'll need to run `git rebase --continue`.
- **`squash` (or `s`)**: You want to combine this commit into the previous commit. Git will then open an editor to let you edit the combined commit message.
- **`fixup` (or `f`)**: Similar to `squash`, but it discards the commit message of the current commit and uses the message of the previous commit.
- **`drop` (or `d`)**: You want to completely remove this commit from the history. **Use this with caution!**

## Example: Squashing Commits

Let's say you have the following commits on your feature branch:

```
Commit A: Added initial structure
Commit B: Implemented login form
Commit C: Fixed a typo in the form
Commit D: Added styling to the form
```

You might want to squash commits B, C, and D into a single commit called "Implement user login feature." To do this, you would run `git rebase -i HEAD~4` (assuming these are the last four commits). In the editor, you would change the commands to look like this:

```
pick <hash_A> Commit A: Added initial structure
squash <hash_B> Commit B: Implemented login form
fixup <hash_C> Commit C: Fixed a typo in the form
squash <hash_D> Commit D: Added styling to the form
```

After saving and closing the editor, Git will perform the rebase. It will then likely open another editor asking you to create the commit message for the squashed commit (combining the messages from B and D, as we used `fixup` for C). You might edit this to say:

```
Implement user login feature

This commit adds the login form with styling and fixes a typo.
```

After saving this message, your history will now look like:

```
Commit A: Added initial structure
Commit E: Implement user login feature
```

Where Commit E is the result of squashing B, C, and D.

## Example: Rewording a Commit Message

If you want to change the message of a specific commit (e.g., "Fix typo" to "Fix: Typo in user registration form"), you would use the `reword` command in the interactive rebase editor. Git will then prompt you to enter the new commit message for that commit.

## Example: Editing a Commit

If you need to change the content of an older commit, you would use the `edit` command. Git will stop at that commit during the rebase, allowing you to make changes, stage them, and then amend the commit using `git commit --amend`. After that, you would run `git rebase --continue` to proceed with the rest of the rebase.

## Aborting an Interactive Rebase

If at any point during the interactive rebase you decide you don't want to continue, you can abort the process using:

```bash
git rebase --abort
```

This will take you back to the state you were in before you started the rebase.

## Conclusion

Interactive rebasing is a powerful tool for cleaning up and refining your Git commit history. It allows you to make your history more understandable and maintainable before sharing your work. However, remember the golden rule: **don't rebase commits that have already been pushed to a shared remote repository** to avoid disrupting your collaborators' work.

## Next Steps

In the next lesson, we will explore another useful Git tool called **Git Reflog**, which can help you recover from accidental actions and understand changes to your repository's history.

```

```
