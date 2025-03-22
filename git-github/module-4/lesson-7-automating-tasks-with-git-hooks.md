Okay, let's proceed with **Module 4: Advanced Git Topics**, **Lesson 7: Automating Tasks with Git Hooks**. We'll plan the content for the file `git-github/module-4/lesson-7-automating-tasks-with-git-hooks.md`.

---

# Module 4: Advanced Git Topics

## Lesson 7: Automating Tasks with Git Hooks

As you become more comfortable with Git, you might start thinking about ways to automate certain tasks within your development workflow. **Git Hooks** provide a powerful mechanism to do just that. Think of them as setting up automatic triggers that run scripts before or after specific Git events occur.

## What are Git Hooks?

Git Hooks are scripts that Git can execute automatically at various points in the Git lifecycle. These points include actions like committing, pushing, receiving pushes, and more. By writing scripts that Git can run at these specific times, you can automate checks, enforce policies, or trigger other processes as part of your version control workflow.

## Why Use Git Hooks?

Git Hooks can be used for a wide range of automation tasks, including:

- **Enforcing Code Style:** You can set up a hook to automatically check your code for style violations (e.g., using linters) before allowing a commit.
- **Running Tests:** Ensure that all unit tests pass before you can push your code to a shared repository.
- **Validating Commit Messages:** Enforce a specific format for your commit messages to maintain consistency.
- **Deploying Code:** Automatically trigger deployment scripts when code is pushed to a specific branch on the server.
- **Notifications:** Send notifications (e.g., emails, Slack messages) when certain Git events occur.

## Types of Git Hooks

Git Hooks are broadly categorized into two types:

- **Client-side Hooks:** These hooks run on your local machine and are triggered by actions you perform locally, such as committing, merging, or pushing.
- **Server-side Hooks:** These hooks run on the Git server and are triggered by actions like receiving pushed commits.

Here are some of the commonly used hooks:

**Client-side Hooks (in `.git/hooks`):**

- **`pre-commit`:** Runs before a commit is made. Typically used to inspect the snapshot being committed (e.g., run tests, check code style). If this script exits with a non-zero status, the commit is aborted.
- **`prepare-commit-msg`:** Runs before the commit message editor is launched but after the default message is created. Often used to programmatically edit the commit message (e.g., add a ticket number).
- **`commit-msg`:** Runs after the commit message has been entered but before the commit is finalized. Can be used to validate the commit message format. If it exits non-zero, the commit is aborted.
- **`pre-rebase`:** Runs before you rebase anything. Can be used to prevent rebasing in certain conditions.
- **`post-checkout`:** Runs after a successful `git checkout`. Often used to set up your working directory appropriately for the checked-out branch.
- **`post-merge`:** Runs after a successful `git merge`. Can be used to perform tasks like updating dependencies.
- **`pre-push`:** Runs before you push any commits to a remote repository. Can be used to run tests or perform other checks to ensure you're not pushing broken code. If it exits non-zero, the push is aborted.

**Server-side Hooks (in `.git/hooks` on the server):**

- **`pre-receive`:** Runs when the server receives a push but before any references are updated. Can be used to enforce policies like commit message formats or prevent pushes to certain branches. If it exits non-zero, all pushed references are rejected.
- **`update`:** Runs once for each branch being updated by a push. Can be used to enforce branch-specific policies. If it exits non-zero, the update of that branch is rejected.
- **`post-receive`:** Runs after all references have been updated. Typically used to trigger other processes like continuous integration builds, deployments, or sending notifications.

## Hook Script Locations

The hook scripts for each Git repository are stored in the `.git/hooks` directory within that repository. When you initialize a new Git repository, this directory is created, and it contains several example hook scripts with a `.sample` extension. To enable a hook, you need to remove the `.sample` extension and make the script executable.

## Example Hook Scripts

Let's look at a couple of simple examples:

**1. `pre-commit` hook (to check for trailing whitespace - written in Python):**

Create a file named `pre-commit` (without any extension) in the `.git/hooks` directory with the following content:

```python
#!/usr/bin/env python3

import sys
import subprocess

def check_trailing_whitespace():
    errors =
    output = subprocess.check_output(['git', 'diff', '--cached', '--check']).decode('utf-8')
    for line in output.splitlines():
        if line.endswith(' '):
            errors.append("Error: Found trailing whitespace.")
            break  # Only need to find one instance to fail the commit
    if errors:
        print("\n".join(errors))
        sys.exit(1)

if __name__ == "__main__":
    check_trailing_whitespace()
```

Then, make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

Now, every time you try to commit, this script will run. If it finds any trailing whitespace in your staged files, it will print an error and prevent the commit from happening.

**2. `pre-push` hook (to run a simple test - written in Shell):**

Create a file named `pre-push` in the `.git/hooks` directory with the following content:

```bash
#!/bin/sh

echo "Running tests before push..."
if ./run_tests.sh; then
  echo "All tests passed. Allowing push."
  exit 0
else
  echo "Tests failed. Aborting push."
  exit 1
fi
```

Make sure you have a script named `run_tests.sh` in your project that executes your tests. Then, make the `pre-push` script executable:

```bash
chmod +x .git/hooks/pre-push
```

Now, before you push your code, this script will run your tests. If the tests fail (exit with a non-zero status), the push will be aborted.

## Creating and Using Hooks

To use a Git hook:

1.  Navigate to the `.git/hooks` directory in your repository.
2.  Choose the hook you want to use based on the event you want to trigger on (e.g., `pre-commit` for before a commit).
3.  Create a file with the name of the hook (without the `.sample` extension).
4.  Write your script in your preferred scripting language (make sure the first line specifies the interpreter, e.g., `#!/bin/bash` or `#!/usr/bin/env python3`).
5.  Make the script executable using `chmod +x <hook_name>`.

## Important Considerations

- **Not Version Controlled:** The hook scripts in the `.git/hooks` directory are not tracked by Git and are local to each repository. This means that if you want to share hooks with your team, you'll need to find other methods, such as including the hook scripts in a separate directory within your repository (e.g., `.githooks`) and then having developers manually link them into their `.git/hooks` directory or using a tool to manage this.
- **Bypassing Hooks:** Sometimes, you might need to bypass a client-side hook (e.g., if you're making a quick fix and don't want to run all the tests). You can usually do this using the `--no-verify` option with commands like `git commit --no-verify` or `git push --no-verify`. However, use this with caution as it can circumvent important checks.

## Analogy: Automatic Actions

Think of Git Hooks like setting up automatic replies in your email or creating rules to sort emails into folders. You define a trigger (a Git event) and an action (your script) that should happen when that trigger occurs.

## Conclusion

Git Hooks provide a powerful way to automate various aspects of your development workflow, from enforcing code quality to triggering deployment processes. By leveraging client-side and server-side hooks, you can ensure consistency, improve code quality, and streamline your team's development process.
