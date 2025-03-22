# Module 2: Working with Branches

## Lesson 5: Undoing Changes with `git reset`

As developers, we often make mistakes or change our minds about the changes we've made. Git provides several ways to undo these changes, and the `git reset` command is a powerful tool for this purpose. It allows you to move the current branch pointer to a previous commit and optionally modify the staging area and working directory.

**Important Caution:** `git reset` can have significant consequences, especially the `--hard` option, which can lead to data loss if used incorrectly. Understand the different modes carefully before using this command.

## Levels of Undo in Git

Before we dive into `git reset`, let's briefly recap the different areas where you might want to undo changes:

- **Working Directory:** Changes you've made to files but haven't yet added to the staging area (using `git add`).
- **Staging Area:** Changes you've added to the staging area but haven't yet committed (using `git commit`).
- **Last Commit:** Changes you've already committed to the repository.

`git reset` can be used to undo changes in the latter two areas. For changes in the working directory that haven't been staged, you might use `git restore` (which we haven't covered in detail yet, but is another way to discard local changes).

## `git reset --soft <commit>`

The `--soft` mode is the least destructive option of `git reset`.

- **What it does:** It moves the branch pointer to the specified `<commit>`. The staging area and your working directory remain unchanged. This means that the changes from the commits that are now "after" the new pointer position are still staged and in your working directory.
- **Use case:** This is often used when you made a commit but realized you forgot to include some changes. You can `git reset --soft HEAD^` (to move back one commit), stage the additional changes, and then commit again, effectively amending your last commit.

**Example:**

Suppose you made a commit with message "Added initial code" and then realized you forgot a file.

```bash
git reset --soft HEAD^
# Now the last commit is undone, but the changes are still staged.
git add forgotten_file.js
git commit --amend -m "Added initial code including forgotten file"
```

Here, `HEAD^` refers to the commit before the current `HEAD`.

## `git reset --mixed <commit>` (Default)

The `--mixed` mode is the default behavior of `git reset` if you don't specify a mode.

- **What it does:** It moves the branch pointer to the specified `<commit>` and resets the staging area to match that commit. However, the changes in your working directory are preserved. This means the changes from the commits that are now "after" the new pointer position are no longer staged but are still present in your working files.
- **Use case:** This is useful if you made a commit and want to unstage the changes but keep them in your working directory so you can modify them or commit them differently.

**Example:**

Suppose you made a commit with several files but now want to unstage them all:

```bash
git reset --mixed HEAD^
# Now the last commit is undone, and the files are no longer staged,
# but they are still in your working directory.
git status
# You would see the files listed under "Changes not staged for commit".
```

You could then selectively stage and commit the files as needed.

## `git reset --hard <commit>`

The `--hard` mode is the most destructive option of `git reset`.

- **What it does:** It moves the branch pointer to the specified `<commit>` and resets both the staging area and the working directory to match that commit. **Any changes in your working directory since that commit will be permanently lost.**
- **Use case:** This should be used with extreme caution and typically only when you are absolutely sure you want to discard all changes since a particular commit.

**Example:**

Suppose you made some experimental commits that you now want to completely get rid of:

```bash
git reset --hard <commit_hash_before_experiments>
# This will move your branch back to the specified commit,
# and all changes made after that commit will be gone from
# your staging area and working directory.
```

**Warning:** Be very careful when using `git reset --hard`, especially if you haven't committed your work. It can lead to irreversible data loss.

## Using `git reset` without a Commit (for unstaging)

You can also use `git reset` without specifying a commit to unstage files that you have added with `git add`, while keeping the changes in your working directory.

```bash
git reset HEAD <file>
```

This command will remove the `<file>` from the staging area.

**Example:**

You accidentally staged a file you didn't want to commit:

```bash
git add sensitive_data.txt
git status
# You'll see sensitive_data.txt is staged.
git reset HEAD sensitive_data.txt
git status
# Now sensitive_data.txt is no longer staged but is still in your working directory.
```

## Comparing `git reset` with `git checkout` and `git revert`

It's important not to confuse `git reset` with other commands that undo changes:

- **`git checkout`**: As we learned, `git checkout` is primarily used for switching between branches or for checking out specific commits (which leads to a detached HEAD state). It can also be used to discard changes in your working directory for a specific file and revert it to the version in the staging area or the last commit.

- **`git revert`**: The `git revert` command is used to undo the changes introduced by a specific commit by creating a new commit that has the opposite effect. This is a safer way to undo changes, especially on shared branches, as it preserves the history of your repository. We will likely cover `git revert` in more detail later.

## When to Use Which `git reset` Mode

- Use `git reset --soft` to amend the last commit or combine commits without losing your staged changes.
- Use `git reset --mixed` (or just `git reset`) to unstage changes while keeping them in your working directory.
- Use `git reset --hard` with extreme caution when you want to completely discard changes in your working directory and staging area back to a specific commit.
- Use `git reset HEAD <file>` to unstage a specific file.

## Conclusion

The `git reset` command is a powerful tool for undoing changes at different stages in your local Git repository. Understanding the different modes (`--soft`, `--mixed`, `--hard`) and their implications is crucial to using it effectively and avoiding accidental data loss. Always be sure of what you are doing before running `git reset`, especially with the `--hard` option.

## Next Steps

In the next lesson, we will learn about the `git rm` and `git mv` commands, which are used for removing and renaming files within your Git repository.

```

```
