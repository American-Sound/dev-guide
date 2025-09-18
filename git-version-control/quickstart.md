# Git and GitHub Quickstart

## Table of Contents

* [Disclaimer](#disclaimer)
* [Installing Git](#installing-git)
* [Configuration](#configuration)
    * [Configuring Git Locally](#configuring-git-locally)
    * [SSH Keys](#ssh-keys)
* [Cloning a Repository](#cloning-a-repository)
* [Creating a Branch](#creating-a-branch)
* [Commit Changes](#commit-changes)
* [Opening a Pull Request](#opening-a-pull-request)

## Disclaimer

This document is a work in progress. Currently, it is under the assumption that the user is using Git at the command line, as it was intended to be used. Check back in the future for information regarding Git GUI tools, such as Git for Windows GUI or Tortoise Git's GUI utility.

## Installing Git

This document was written under the assumption that the user is either

1. Working on Windows or

2. Is working on Linux, and knows how to install Git on their respective distribution.

Thus, installation instructions will only be provided for Windows at this time. Linux instructions may or may not be provided in the future.

Windows users should use the following steps to install Git:

1. Navigate to [https://gitforwindows.org/](https://gitforwindows.org/) and click `Download`

2. Scroll down, and under assets, you will choose the appropriate file to download. In *most* cases, this will be called something along the lines of `Git-<version>-64-bit.exe`. This is the installer for the `x86-64`-compatible version of Git, which would be the case for most Windows machines. As of writing this, that file is at the top of the list and is called `Git-2.51.0-64-bit.exe`. Click on that file to download it, then run the downloaded executable of the same name. **Don't mindlessly click through the installer**, follow the next steps carefully.

3. On the **Select Components**, be sure that the following are checked:

![Correct features to select](./img/checked-options.png)

4. For the **Default Editor Used by Git**, you will want to choose your software of choice. I recommend [VSCode](https://code.visualstudio.com/) or [Notepad++](https://notepad-plus-plus.org/), but **make sure that whatever you use is already installed before you move forward**. If you don't know what to do, then just select basic Notepad.

5. For **Adjusting the name of the initial branch in new repositories**, this doesn't matter too much unless you know what you would want for this. Either **Let Git Decide**, or **Overrride** with `main` or `master`. 

6. For **Adjusting your PATH environment**, you should select **Git from the command line and also from 3rd-party software**.

7. For **Choosing the SSH executable**, I recommend you select **Use bundled OpenSSH** unless you have a reason for doing otherwise.

8. For **Choosing HTTPS transport backend**, you should **Use the native Windows Secure Channel Library** unless you have a reason for doing otherwise.

9. This is a **very important step** that you do not want to mess up. For **Configuring the line ending conversions**, you should **Checkout Windows-style, commit Unix-style line endings**. This will save you a lot of trouble in the future, and not doing so is a massive headache.

10. For **Configuring the terminal emulator to use with Git Bash**, I recommend you **Use MinTTY (the default terminal of MSYS2)**, but if you are more comfortable with Powershell, feel free to opt for that instead.

11. For **Choose hte default behavior of `git pull`**, you should choose **Fast-forward or merge**. If you don't understand what these mean, don't worry, but you will see the terms **merge** versus **rebase** a lot, and they are important to know about when working with Git.

12. For **Choose a credential helper**, you should choose **Git Credential Manager**.

13. For **Configuring extra options**, I recommend **Enable file system caching** only.

14. Click install, and after it is finished I recommend **rebooting your PC**.

## Configuration

### Configuring Git Locally

Configuring Git is easy. Open Git bash, and type the following, filling in values between `<>` with the appropriate information. Do not include the `<>` symbols, they are simply for showing you where to fill in your own information. Note, **your email address should match the one linked to your GitHub account**.

```bash
git config --global user.name "<Your Name>" # Note the quotes
git config --global user.email <YourEmailAddress>
```

### SSH Keys

This part is very important for two reasons:

1. You don't *always* need to do this step, necessarily, but the rest of this guide and many online guides will have expected you to have done so.

2. This is the industry standard way of using Git with remote repositories.

It is worth noting that the process of doing this on GitHub is very similar for most popular Git clients.

Login to GitHub, click on your profile picture, and then click on `Settings`.

![Settings](./img/settings-box.png)

In the left pane, click on `SSH and GPG keys`.

![SSH and GPG keys](./img/ssh-and-gpg.png)

In the main pane, click on `New SSH Key` in the top right.

![New SSH Key](./img/new-ssh-key.png)

You will now see three things:

1. A text box for the `Title` of our key.

2. A dropdown for our `Key type`.

3. A text box for the `Key` itself.

Leave this window open, we are going to fill out the information shortly. For now, open Git bash as you did before if it isn't already open. In Git bash, type the following command:

```bash
ssh-keygen -t ed25519 -C "<The same email address as before>"
```

After you run the command, you will be prompted with:

```bash
> Enter a file in which to save the key (/home/YOU/.ssh/id_ALGORITHM):[Press enter]
```

I recommend leaving the field blank, and it will use that `/home/YOU/.ssh/id_ALGORITHM` path as the default. Note that path, we will use it shortly.

You will then be prompted for a password. **The password will not show as you type it** as a form of security.

```bash
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

Now, in Git Bash, type the following command using the path we noted a couple of steps before this. **Notice the addition of the `.pub` file extension**.

```bash
cat /home/YOU/.ssh/id_ALGORITHM.pub
```

The `cat` command simply displays the contents of that `.pub` file. This is the SSH key that we will be entering on GitHub.

Open the browser window with our GitHub tab still open. Give the key a title, it can be anything (Mine is simply "Thinkpad-Laptop"). Leave the `Key type` as `Authentication Key`. Copy the contents of your `.pub` file, that is, the entire contents:
`ssh-ed25519 <a bunch of seemingly random characters> <your email>` into the `Key` field. Finally, click `Add SSH Key`.

## Cloning a Repository

The first step in contributing to a code base is to clone the repository. We will be using this repository for all steps going forward. You will need the URL of the repository to clone it, in our case, it is `git@github.com:American-Sound/dev-guide.git`, and you can obtain it by navigating to the repositories front page and clicking the `<> Code` button, selecting `SSH`, and copying the URL as seen below.

![SSH URL](./img/ssh-link.png)

Using that URL, run the following commands in Git Bash:

```bash
git clone git@github.com:American-Sound/dev-guide.git
```

This fetches all of the code from the repo, and places it into a local repository on your computer with the same name. You can list the contents to see what I mean.

```bash
ls -a dev-guide
```

Note the `.git` directory that is listed from that command. That is Git's database that helps it manage the repository and its link the remote repository. **Don't mess with the `.git` directory unless you have a good reason to do so**. Now, we are going to change directories (`cd`) into our local repository.

```bash
cd dev-guide
```

## Creating a Branch

If you followed up to this point, you should be inside of your local repository (`dev-guide/`) in Git Bash. Now, type this command and observe the output:

```bash
git branch
```

This will list all of the branches of the local repository. As of the time that I am writing this, I have no idea how many that may be, nor what they all are. However, you should be able to at least see the primary branch `main`, and it should show as your current branch via an `*` next to it. `* main`. The `main` branch is typically where our most up-to-date code is held, meaning that code that is complete, tested, and confirmed to work is located in our `main` branch. When we make changes to code, we want to `checkout` a new branch to make changes to the code. Later, when the code is ready, we will `merge` it into the `main` branch, but for now, we are going to isolate our work to prevent interfering with other people's. Run the following command

```bash
git checkout -b <your-name>-test-branch
```

If you run `git branch` again, you'll see that you are now checked out in a new branch with the name you just gave it. Now, let's practice editing the code. In a text editor of your choice, open the file `dev-guide/git-version-control/who.txt`. You should see a list of names or, if you're the first person to do this, just my name (Carter D). Add your name on a new line at the bottom of that text file. Save the file, then run the following command:

```bash
git status
```

This will list the files you have made changes to, with the exceptions of files or file patterns specified in the `.gitignore` if it is present. As a small note, `.gitignore` is how you tell git to not track files or groups of files in your repository. Anyway, as I said, you should see `dev-guide/git-version-control/who.txt` listed as having untracked changes. We are now ready to make a commit of our changes to the current branch.

## Commit Changes

The first thing we will need to do is add our changes to the next commit. We do this with the following command:

```bash
git add .
```

I owe you an explanation here. You could probably guess what `git add` does, but what about `.`? In Unix-like terminal environments, `.` represent the **current working dirctory**. When adding files, we could have specified exactly which file to commit, thus

```bash
git add dev-guide/git-version-control/who.txt
```

would have been perfectly valid. However, it is **rarely** a good idea to only commit one, a few, or any amount less than **all** of the files you have changed unless you have a good reason for doing so. Thus, we are adding to our commit **all changed files** in our current working directory using

```bash
git add .
```

just to be safe. Now, it's time to actually make the commit and send it to our remote repository. Run the following to do so:

```bash
git commit -m "<Your name>'s test commit"
git push origin <your-name>-test-branch
```

The first command will make the commit itself with a message (`-m`) specified within quotes. The second command will push it to the remote repository. The latter will ask for your password that we set in the [ssh configuration](#ssh-keys) step. Since you haven't pushed to this new branch, it will create the branch in the remote repository.

## Opening a Pull Request

Return to the GitHub page for the remote repository. By default, the branch shown will be `main`, but you'll be selecting your branch from the list.

![Branches](./img/branch-selection.png)

Select your branch. Navigate to the file we edited, `dev-guide/git-version-control/who.txt`, and observe your name present. If you want, you can switch back the main branch and see that your name is not present. However, the best way to view differences between branches would be to view the `diff`.