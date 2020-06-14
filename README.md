<p align="center">
  <a>
    <img src="pictures/cover-pic.jpeg" width="300" height="150">
  </a>
</p>
<h2 align="center">Getting Started With Git and Github</h2>
<h4 align="center">This project will demonstrste the working flow of Git and Github</h4>

## Table of contents

- [Setting up Github Account](#setting-up-github-acccount)
- [Setting up Git on your Local machine](#setting-up-git-on-your-local-machine)
- [Setting up SSH keys for your git and github account](#setting-up-ssh-keys-for-your-git-github-acccount)
- [Git WorkFlow](#git-workflow)
- [Working with Local Repository](#working-with-local-repository)
- []




## Setting up Github Account

1. Go to [GitHub](github.com)
2. Signup using a valid gamail account and setup password
3. Explore the options for further setting of your profile

## Setting up Git on your Local machine

1. Download git from https://www.atlassian.com/git/tutorials/install-git (according to your operating system + follow the instruction at the site)
2. For windows select both git bash and command prompt option during the installation process and for other options keep the default
3. Open git bash
4. Run the following command:

```bash
$ git config --global user.name "Your name(may the github user name)"
$ git config --global user.email "your email(may the email used to signup github)"
```

## Setting up SSH keys for your git and github account

You can follow the link https://help.github.com/en/github/authenticating-to-github/about-ssh
or you can follow the steps bellow:

**About SSH:**

Using the SSH protocol, you can connect and authenticate to remote servers and services.
With SSH keys, you can connect to GitHub without supplying your username or password at each visit.
When you set up SSH, you'll generate an SSH key and add it to the ssh-agent and then add the key to your GitHub account.
Adding the SSH key to the ssh-agent ensures that your SSH key has an extra layer of security through the use of a passphrase.

1.Open Terminal or Git Bash.

2.Paste the text below, substituting in your GitHub email address.

    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    > Generating public/private rsa key pair.
    > When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
    > Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
    > Enter passphrase (empty for no passphrase): [Type a passphrase]
    > Enter same passphrase again: [Type passphrase again]

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

    ![Find Settings](pictures\1.png)

    d. In the user settings sidebar, click SSH and GPG keys.

    ![In the Setting Option](pictures\2.png)

    e. Click New SSH key or Add SSH key.

    ![In the SSH and GPG eys Option](pictures\3.png)

    f. In the "Title" field, add a descriptive label for the new key.
    For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

    g. Paste your key into the "Key" field.

    ![In the New SSH key Option](pictures\4.png)

    h. Click Add SSH key.

    ![Click the Button](pictures\5.png)

    i. If prompted, confirm your GitHub password.

    ![Enter GitHub acccount password](pictures\6.png)

### **_If you want to change the passphrase of your SSH key_**

You can change the passphrase for an existing private key without regenerating the keypair by typing the following command:

    $ ssh-keygen -p
    > Enter file in which the key is (/Users/you/.ssh/id_rsa): [Hit enter]
    > Key has comment '/Users/you/.ssh/id_rsa'
    > Enter new passphrase (empty for no passphrase): [Type new passphrase]
    > Enter same passphrase again: [One more time for luck]
    > Your identification has been saved with the new passphrase.

If your key already has a passphrase, you will be prompted to enter it before you can change to a new passphrase.

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

![image](pictures\7.png)

3. To make this folder a Git repository, type the following command:

> \$git init

![image](pictures\8.png)

This will initialize the folder as a Git repository with a hidden folder named **.git**. Notice changed prompt (master) as the pricipal branch of your repository.

You can still check the folder by the following command:

> \$ls -la

![image](pictures\9.png)

4. Now you can start your project by adding any number of file of any kind in the folder.
   For example if we add a text.txt file in the folder and then run the following command:
   > \$git status

![image](pictures\10.png)

You can see an untraced file named text.txt as this file is now in our workspace.
Will call this as our working copy.

5. To stage this file for git repository run the following command:

> \$git add .

**Note:** Here a period(**.**) is used to add all file to staging area from the workspace.
You can add specific file by replacing the period with file name.

![image](pictures\11.png)

You can see the difference by running **\$git status** again.

You can also run:

> \$git diff

This shows nothing as there is no difference between your working copy and the staging area.

![image](pictures\15.png)

Now if you want to unstage the file due any reason, run the following command:

> \$git rm --cached filename

6. This the most important step. Now if you are satisfied with your work and ready
   to commit your work to the git repository, run the following command:

> \$git commit -m "Descriptive messages"

Within double qoute (""), please enter a total Descriptive message of your status of the commit
as you will see this message next time you want to check the commit history. A proper
message will help you to understand the commit history better.

![image](pictures\12.png)

7.  Now if you run the **\$git status** command again, you will see that you git repository
    is up to date and nothing to be committed.

![image](pictures\13.png)

You can aslo run:

> \$git diff --staged

This shows nothing, as there is no difference between your staged copy and git repository.

**Note:** **\$git diff** command at step 5 shows the difference between the working copy
and the staging area. On the other hand

**\$git diff --staged** command shows the difference between the staging area and the git repository.

8. Now you can see your commit history by running:

> \$git log

This command shows you all the commit history with a unique string of charectes and the date and time of committing
as well as the messages you
put at the time of committing.

![image](pictures\14.png)

9. Now you can continue your work with the files you have in the folder/directory you are working.
   And to update your work in the git repository please repeat the steps from step 5.
[Book]