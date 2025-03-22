# Module 2: Working with Branches

## Lesson 4: Exploring Changes with `git diff`

In our Git workflow, we frequently make changes to our files. It's crucial to be able to see exactly what those changes are before we stage and commit them. The `git diff` command is your primary tool for this purpose. It allows you to compare different versions of your files in your Git repository.

## Understanding the Basics

The `git diff` command essentially shows you the difference between two snapshots in Git. These snapshots can be your working directory, the staging area, or specific commits in your history.

## `git diff` (Working Directory vs. Staging Area)

When you run `git diff` without any specific arguments, it shows you the changes you've made in your **working directory** that have **not yet been staged** for the next commit.

**Example:**

Let's say you modified a file named `my_document.txt` after your last commit and haven't used `git add` yet. Running `git diff` will show you these unstaged changes:

```bash
git diff
diff --git a/my_document.txt b/my_document.txt
index 1234567..89abcdef 100644
--- a/my_document.txt
+++ b/my_document.txt
@@ -1,2 +1,2 @@
 This is the original content of the document.
-I have made some new changes here.
+I have made some updated changes here.
```

- The lines starting with `--- a/` indicate the original version of the file.
- The lines starting with `+++ b/` indicate the modified version of the file.
- Lines starting with `-` show what was removed.
- Lines starting with `+` show what was added.

## `git diff --staged` or `git diff --cached` (Staging Area vs. Last Commit)

To see the changes that you have **staged** (using `git add`) and that will be included in your next commit, you can use the `--staged` or `--cached` option with `git diff`. These options are synonymous.

**Example:**

After running `git add my_document.txt`, if you run `git diff --staged`:

```bash
git diff --staged
diff --git a/my_document.txt b/my_document.txt
index 1234567..89abcdef 100644
--- a/my_document.txt
+++ b/my_document.txt
@@ -1,2 +1,2 @@
 This is the original content of the document.
-I have made some new changes here.
+I have made some updated changes here.
```

This output shows the changes that are ready to be committed.

## `git diff HEAD` (Working Directory vs. Last Commit)

If you want to see all the changes you've made in your working directory since your last commit, regardless of whether they are staged or not, you can use `git diff HEAD`. `HEAD` refers to the last commit on the current branch.

**Example:**

If you have both staged and unstaged changes in `my_document.txt`, `git diff HEAD` will show you all of them.

```bash
git diff HEAD
diff --git a/my_document.txt b/my_document.txt
index 1234567..cdefghi 100644
--- a/my_document.txt
+++ b/my_document.txt
@@ -1,2 +1,3 @@
 This is the original content of the document.
-I have made some new changes here.
+I have made some updated changes here.
+And I have added a new line that is not yet staged.
```

This output will include both the staged and unstaged modifications.

## `git diff <commit>` (Working Directory vs. a Specific Commit)

You can also compare your working directory with a specific commit in the past by providing the commit's hash to `git diff`.

**Example:**

To compare your current working directory with the commit that has the hash `a1b2c3d`:

```bash
git diff a1b2c3d my_document.txt
```

This will show the differences between the specified commit's version of `my_document.txt` and the version in your working directory. You can omit the filename to see differences across all files.

## `git diff <commit1> <commit2>` (Comparing Two Commits)

To see the changes introduced between two specific commits, you can provide the hashes of both commits to `git diff`.

**Example:**

To see the changes between commit `e5f6g7h` and commit `a1b2c3d`:

```bash
git diff e5f6g7h a1b2c3d
```

This will show you all the changes that occurred between these two points in your project's history.

## `git diff <branch1> <branch2>` (Comparing Two Branches)

Similarly, you can compare the latest commits of two different branches to see the differences between them.

**Example:**

To see the differences between the `main` branch and a branch named `feature-x`:

```bash
git diff main feature-x
```

This will show you the changes that are present in `feature-x` but not in `main` (or vice versa, depending on the order).

## Useful Options for `git diff`

Here are some helpful options you can use with `git diff`:

- **`--color-words`**: Instead of showing changes line by line, this option highlights the specific words that have changed within a line. This can be very useful for seeing small text modifications.

  ```bash
  git diff --color-words
  ```

- **`--ignore-space-change`**: This option ignores changes in the amount of whitespace.

  ```bash
  git diff --ignore-space-change
  ```

- **`-w` or `--ignore-all-space`**: These options ignore all whitespace changes when comparing lines.

  ```bash
  git diff -w
  ```

- **`--stat`**: This option provides a brief summary of the changes, showing which files were modified and the number of lines added or removed.

  ```bash
  git diff --stat
  ```

## Conclusion

The `git diff` command is an indispensable tool for any Git user. It allows you to thoroughly inspect the changes you've made at various stages of your workflow, compare different points in your history, and understand the differences between branches. Regularly using `git diff` will help you ensure that you are staging and committing exactly what you intend to.

## Next Steps

In the next lesson, we will learn about the `git reset` command, which allows you to undo changes at different levels in your Git repository.

```

