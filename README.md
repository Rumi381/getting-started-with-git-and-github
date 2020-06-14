<p align="center">
  <a>
    <img src="pictures/cover-pic.jpeg" width="300" height="150">
  </a>
</p>
<h2 align="center">Getting Started With Git and Github</h2>
<h4 align="center">This project will demonstrste the working flow of Git and Github</h4>

### Table of contents

- [Setting up Github Account](#setting-up-github-acccount)
- [Setting up Git on your Local machine](#setting-up-git-on-your-local-machine)
- [Setting up SSH keys for your git and github account](#setting-up-ssh-keys-for-your-git-github-acccount)
- [Git WorkFlow](#git-workflow)
- [Working with Local Repository](#working-with-local-repository)
- [Viewing Your Staged and Unstaged Change](#viewing-your-staged-and-unstaged-change)
- [Ignoring Files](#ignoring-files)

## Setting up Github Account

1. Go to [GitHub](github.com)
2. Signup using a valid gamail account and setup password
3. Explore the options for further setting of your profile

## Setting up Git on your Local machine

**Note:** I personally recommend that you should have VS Code installed in your machine as this will very handy to work with any type of project
as well as can be used as the base text editor. You can Download it from [Here>>](https://code.visualstudio.com/download)

1. Download git from https://www.atlassian.com/git/tutorials/install-git (according to your operating system + follow the instruction at the site)
2. For windows select both git bash and command prompt option during the installation process and for other options keep the default
3. Open git bash
4. Run the following command:

```bash
$ git config --global user.name "Your name(may the github user name)"
$ git config --global user.email "your email(may the email used to signup github)"
$ git config --global core.editor "code --wait"
```

If you are using Notepad++ as your text editor, then you have to run the following command inplace
of **git config --global core.editor "code --wait"**:

For Notepad++ (Windows 64-bit)

```bash
$ git config --global core.editor "'C:\Program Files\Notepad++\notepad++.exe' -multiInst -notabbar -nosession-noPlugin"
```

If you have a 32-bit editor on a Windows 64-bit system, run the following command instead:

```bash
$ git config --global core.editor "'C:\Program Files (x86)\Notepad++\notepad++.exe' -multiInst -notabbar -nosession-noPlugin"
```

This is the default configuraion for your git in your Local machine. You can check the settings by runnig:

```bash
$ git config --list
```

#

## Setting up SSH keys for your git and github account

You can follow the [link](https://help.github.com/en/github/authenticating-to-github/about-ssh)
or you can follow the steps bellow:

**About SSH:**

Using the SSH protocol, you can connect and authenticate to remote servers and services.
With SSH keys, you can connect to GitHub without supplying your username or password at each visit.
When you set up SSH, you'll generate an SSH key and add it to the ssh-agent and then add the key to your GitHub account.
Adding the SSH key to the ssh-agent ensures that your SSH key has an extra layer of security through the use of a passphrase.

1. Open Terminal or Git Bash.

2. Paste the text below, substituting in your GitHub email address.

```bash
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Please replace the email with the email you configured above.
You will be prompted to enter password like bellow for your SSH key:

```bash
> Generating public/private rsa key pair.
#When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
> Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

3.  **Adding your SSH key to the ssh-agent:**

    a. Start the ssh-agent in the background.

        $ eval "$(ssh-agent -s)"
        > Agent pid 59566

    b. Add your SSH private key to the ssh-agent.

        $ ssh-add ~/.ssh/id_rsa

4.  **Add the SSH key to your GitHub account:**

    a. Copy the SSH key to your clipboard:

         $ clip < ~/.ssh/id_rsa.pub

    This command copies the contents of the id_rsa.pub file to your clipboard
    which you can paste to your GitHub acccount.

    b. Go to your github account

    c. In the upper-right corner of any page, click your profile photo, then click Settings.

<p align="center">
  <a>
    <img src="pictures/1.png">
  </a>
</p>

d. In the user settings sidebar, click SSH and GPG keys.

<p align="center">
  <a>
    <img src="pictures/2.png">
  </a>
</p>

e. Click New SSH key or Add SSH key.

<p align="center">
  <a>
    <img src="pictures/3.png">
  </a>
</p>

f. In the "Title" field, add a descriptive label for the new key.
For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

g. Paste your key into the "Key" field.

<p align="center">
  <a>
    <img src="pictures/4.png">
  </a>
</p>
    h. Click Add SSH key.

<p align="center">
  <a>
    <img src="pictures/5.png">
  </a>
</p>

i. If prompted, confirm your GitHub password.

<p align="center">
  <a>
    <img src="pictures/6.png">
  </a>
</p>

### **_If you want to change the passphrase of your SSH key_**

You can change the passphrase for an existing private key without regenerating the keypair by typing the following command:

```bash
$ ssh-keygen -p
```

You will be prompted as bellow:

```bash
> Enter file in which the key is (/Users/you/.ssh/id_rsa): [Hit enter]
> Key has comment '/Users/you/.ssh/id_rsa'
> Enter new passphrase (empty for no passphrase): [Type new passphrase]
> Enter same passphrase again: [One more time for luck]
> Your identification has been saved with the new passphrase.
```

If your key already has a passphrase, you will be prompted to enter it before you can change to a new passphrase.

#

<p align="center">
  <a>
    <img src="pictures/gitlogo.png" width="200" height="200">
  </a>
</p>
<h2 align="center">Git WorkFlow</h2>

## Git WorkFlow

This section will demonstrste the most common workflow of git to start a git repository.

## Working with Local Repository

1. Select a folder/directory on your computer

1. Right Click on the folder and select open Git Bash here

<p align="center">
  <a>
    <img src="pictures/7.png">
  </a>
</p>

3. To make this folder a Git repository, type the following command:

> \$git init

<p align="center">
  <a>
    <img src="pictures/8.png">
  </a>
</p>

This will initialize the folder as a Git repository with a hidden folder named **.git**. Notice changed prompt (master) as the pricipal branch of your repository.

You can still check the folder by the following command:

> \$ls -la

<p align="center">
  <a>
    <img src="pictures/9.png">
  </a>
</p>

4. Now you can start your project by adding any number of file of any kind in the folder.
   For example if we add a text.txt file in the folder and then run the following command:
   > \$git status

<p align="center">
  <a>
    <img src="pictures/10.png">
  </a>
</p>

You can see an untraced file named text.txt as this file is now in our workspace.
Will call this as our working copy.

5. To stage this file for git repository run the following command:

> \$git add .

**Note:** Here a period(**.**) is used to add all file to staging area from the workspace.
You can add specific file by replacing the period with file name.

<p align="center">
  <a>
    <img src="pictures/11.png">
  </a>
</p>

You can see the difference by running **git status** again.

Now if you want to unstage the file due any reason, run the following command:

```bash
$ git rm --cached filename
```

6. This the most important step. Now if you are satisfied with your work and ready
   to commit your work to the git repository, run the following command:

```bash
$ git commit -m "Descriptive messages"
```

Within double qoute (""), please enter a total Descriptive message of your status of the commit
as you will see this message next time you want to check the commit history. A proper
message will help you to understand the commit history better.

<p align="center">
  <a>
    <img src="pictures/12.png">
  </a>
</p>

7.  Now if you run the **\$git status** command again, you will see that you git repository
    is up to date and nothing to be committed.

<p align="center">
  <a>
    <img src="pictures/13.png">
  </a>
</p>

8. Now you can see your commit history by running:

```bash
$ git log
```

This command shows you all the commit history with a unique string of charectes and the date and time of committing
as well as the messages you
put at the time of committing.

<p align="center">
  <a>
    <img src="pictures/14.png">
  </a>
</p>

9. Now you can continue your work with the files you have in the folder/directory you are working.
   And to update your work in the git repository please repeat the steps from step 5.

## Viewing Your Staged and Unstaged Change

Suppose you have modified some files, added or deleted some files/directory from your working copy.
Now you can see the status of your working copy before staging by running **git status**

<p align="center">
  <a>
    <img src="pictures/16.png">
  </a>
</p>

If the **git status** command is too vague for you — you want to know exactly what you changed, not
just which files were changed — you can use the **git diff** command. You’ll probably use it most often to answer these two questions: What have you
changed but not yet staged? And what have you staged that you are about to commit? Although git
status answers those questions very generally by listing the file names, git diff shows you the
exact lines added and removed — the patch, as it were.

<p align="center">
  <a>
    <img src="pictures/17.png">
  </a>
</p>

That command compares what is in your working directory with what is in your staging area. The
result tells you the changes you’ve made that you haven’t yet staged.

If you want to see what you’ve staged that will go into your next commit, you can use git diff
--staged. This command compares your staged changes to your last commit:

<p align="center">
  <a>
    <img src="pictures/18.png">
  </a>
</p>

**Note:** If the promp is lengthy, Press enter key repeatedly to proceed with the promt.
Press q to exit at any stage.

## Ignoring Files

Often, you’ll have a class of files that you don’t want Git to automatically add or even show you as
being untracked. These are generally automatically generated files such as log files or files
produced by your build system. In such cases, you can create a file listing patterns to match them
named **.gitignore**.

To create a **.gitignore** file run the following command:

```bash
$ touch .gitignore
```

Now open the **.gitignore** file in the text editor and enter your required files and folder name thats need to be innored.

The rules for the patterns you can put in the .gitignore file are as follows:

- Blank lines or lines starting with # are ignored.
- Standard glob patterns work, and will be applied recursively throughout the entire working
  tree.
- You can start patterns with a forward slash (/) to avoid recursivity.
- You can end patterns with a forward slash (/) to specify a directory.
- You can negate a pattern by starting it with an exclamation point (!).

Here are some way of doing different ignoring operation:

<p align="center">
  <a>
    <img src="pictures/19.png">
  </a>
</p>
