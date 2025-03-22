# Lesson 2: Installing and Setting Up Git

In the previous lesson, we learned what version control is and why it's so important. Now, it's time to get our hands dirty and install Git on our local development machines. This lesson will guide you through the installation process for the most common operating systems and help you configure Git for initial use.

## Checking if Git is Already Installed

Before we proceed with the installation, it's a good idea to check if Git is already installed on your system. Open your terminal (on macOS and Linux) or command prompt (on Windows) and type the following command:

```bash
git --version
```

If Git is installed, you will see a message displaying the Git version. If you get an error like "git: command not found" or something similar, it means Git is not installed, and you should follow the installation instructions below for your operating system.

## Installation Guide

Choose the instructions that correspond to your operating system:

### 1. Installing Git on Windows

1.  **Download the Git for Windows Installer:** Go to the official Git for Windows website: [https://git-scm.com/download/win](https://git-scm.com/download/win) and the download should start automatically.

2.  **Run the Installer:** Once the download is complete, double-click the `.exe` file to run the installer.

3.  **Follow the Setup Wizard:**

    - You'll be presented with a series of screens. Read each screen carefully.
    - **License Agreement:** Click "Next" after reviewing the license.
    - **Choose Components:** The default components are usually sufficient. You can leave them as they are and click "Next."
    - **Adjusting your PATH environment:** This is an important step. We recommend choosing the option **"Git from the command line and also from 3rd-party software"**. This will allow you to use Git from the command prompt and other tools. Click "Next."
    - **Choose HTTPS transport backend:** The default option, **"Use OpenSSL library"**, is generally recommended. Click "Next."
    - **Configure line ending conversions:** For most Windows users, the default option **"Checkout Windows-style, commit Unix-style line endings"** is a good choice. Click "Next."
    - **Choose the default terminal emulator to use with Git Bash:** You can choose **"Use MinTTY (the default terminal of MSYS2)"** for a more Unix-like terminal experience, or **"Use Windows' default console window"**. Both will work. Click "Next."
    - **Choose which extra options to enable:** The default options are usually fine. **"Enable file system caching"** and **"Enable Git Credential Manager"** are generally useful. Click "Next."
    - **Configure experimental options:** It's generally recommended to leave these unchecked unless you have a specific reason to enable them. Click "Install."

4.  **Complete the Installation:** Once the installation is finished, you can check the box to "View Release Notes" and click "Finish."

5.  **Verify the Installation:** Open your command prompt and run `git --version`. You should now see the Git version displayed.

### 2. Installing Git on macOS

There are a few ways to install Git on macOS:

**Method 1: Using the Installer (Recommended for Beginners)**

1.  **Download the Git for macOS Installer:** Go to the official Git website: [https://git-scm.com/download/mac](https://git-scm.com/download/mac) and the download should start automatically.

2.  **Run the Installer:** Once the download is complete, double-click the `.pkg` file to run the installer.

3.  **Follow the Installation Prompts:** Follow the on-screen instructions to complete the installation. This is usually a straightforward process.

4.  **Verify the Installation:** Open your Terminal application (you can find it in Applications > Utilities) and run `git --version`. You should see the Git version displayed.

**Method 2: Using Homebrew (for users familiar with package managers)**

If you have Homebrew installed on your macOS system (it's a popular package manager), you can install Git with a single command:

1.  **Open Terminal:** Open your Terminal application.

2.  **Run the Installation Command:** Type the following command and press Enter:

    ```bash
    brew install git
    ```

3.  **Verify the Installation:** Once the installation is complete, run `git --version` in the Terminal to confirm.

**Method 3: Using Xcode Command Line Tools**

If you have Xcode installed on your Mac, Git might already be included. You can try running `git --version` in the Terminal. If it's not installed, macOS might prompt you to install the Command Line Tools, which include Git.

### 3. Installing Git on Linux

The installation process on Linux varies depending on your distribution. Here are instructions for some of the most common distributions:

**Debian or Ubuntu:**

1.  **Open Terminal:** Open your terminal.

2.  **Update Package List:** Run the following command to update the package lists:

    ```bash
    sudo apt update
    ```

3.  **Install Git:** Run the following command to install Git:

    ```bash
    sudo apt install git
    ```

4.  **Verify the Installation:** Once the installation is complete, run `git --version` in the terminal to confirm.

**Fedora, CentOS, or Red Hat Enterprise Linux (RHEL):**

1.  **Open Terminal:** Open your terminal.

2.  **Install Git:** Run the following command using `dnf` (for newer versions) or `yum` (for older versions):

    ```bash
    sudo dnf install git
    ```

    or

    ```bash
    sudo yum install git
    ```

3.  **Verify the Installation:** Once the installation is complete, run `git --version` in the terminal to confirm.

**Other Distributions:**

For other Linux distributions, you can usually find installation instructions on the Git website or your distribution's documentation. The general approach involves using your distribution's package manager.

## Initial Git Configuration

Once Git is installed, you'll want to configure your username and email address. Git uses this information to associate your commits with your identity. It's important to set these correctly.

1.  **Open your terminal or command prompt.**

2.  **Set your username:** Replace `"Your Name"` with your actual name.

    ```bash
    git config --global user.name "Your Name"
    ```

3.  **Set your email address:** Replace `"your.email@example.com"` with your actual email address.

    ```bash
    git config --global user.email "your.email@example.com"
    ```

    **Note:** Using the `--global` option applies these settings to all Git repositories on your system. If you need different usernames or email addresses for specific projects, you can run these commands without the `--global` option when you are inside that project's repository.

## Verifying Your Configuration

You can verify that your username and email have been configured correctly by running the following command:

```bash
git config --global user.name
git config --global user.email
```

This will display the configured values.

## Choosing a Text Editor for Git (Optional but Recommended)

Git often needs to open a text editor for tasks like writing commit messages or resolving merge conflicts. While Git has a default editor, you might want to configure it to use your preferred text editor. Here's how you can set it (replace `code` with the command to open your preferred editor):

```bash
git config --global core.editor "code --wait"  # For Visual Studio Code
# git config --global core.editor "subl -w"      # For Sublime Text
# git config --global core.editor "nano"         # For Nano (command-line editor)
# git config --global core.editor "vim"          # For Vim (command-line editor)
```

Choose the command that corresponds to your text editor. The `--wait` or `-w` flag tells Git to wait for the editor to be closed before continuing.

## Troubleshooting and Common Issues

While the installation process is usually straightforward, you might encounter some common issues. Here are a few troubleshooting tips:

**1. "Command not found" Error After Installation:**

- **Cause:** This usually means that the system's PATH environment variable hasn't been updated to include the Git executable directory.
- **Windows:** During the Git for Windows installation, make sure you selected the option **"Git from the command line and also from 3rd-party software"**. If you didn't, you might need to re-run the installer and choose this option. You might also need to restart your command prompt or even your computer for the changes to take effect.
- **macOS and Linux:** If you used a package manager like Homebrew or `apt`, this issue is less common. However, if you downloaded a standalone installer, ensure that the installation process completed successfully and that Git's installation directory is in your system's PATH. Restarting your terminal might help.

**2. Permission Issues (macOS and Linux):**

- Occasionally, you might encounter permission issues during or after installation. If you see errors related to permissions, you might need to use the `sudo` command (on macOS and Linux) with the installation commands. However, be cautious when using `sudo` and ensure you understand the command you are running. For standard Git installation, this is usually not required.

**3. Terminal or Command Prompt Not Recognizing Commands:**

- **Restart Your Terminal/Command Prompt:** After installing Git, especially on Windows, you might need to close and reopen your terminal or command prompt for the system to recognize the new `git` command.

**4. Issues with Setting Global Configuration:**

- **Typos:** Double-check that you have typed the `git config` commands correctly, especially the `--global` option and the user name and email values.
- **Permissions:** In rare cases, there might be permission issues preventing Git from writing to the global configuration file (`.gitconfig` in your home directory). If you suspect this, you might need to check the permissions of your home directory and its contents.

**5. Firewall or Network Issues During Download:**

- If you are having trouble downloading the Git installer, ensure that your firewall is not blocking the connection to the Git website. This is usually not an issue for standard installations.

**6. Typographical Errors in Commands:**

- Always double-check the commands you type in the terminal. Git commands are case-sensitive, so make sure you have the correct capitalization.

**If you encounter other errors during installation, here are some helpful tips:**

- **Carefully read the error message:** The error message often provides clues about what went wrong.
- **Search online:** Copy and paste the error message into a search engine. You'll likely find others who have encountered the same issue and solutions.
- **Refer to the official Git documentation:** The official Git documentation is a great resource for troubleshooting: [https://git-scm.com/doc](https://git-scm.com/doc)

**Remember:** If you get stuck at any point, don't hesitate to ask for help!

## Conclusion

Congratulations! You have now successfully installed Git on your system and configured your basic identity. In the next lesson, we will start using Git by learning how to create a new Git repository and perform the basic Git workflow of staging and committing changes. Get ready to start tracking your project's history!
