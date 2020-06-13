# Getting Started With Git and Github

This project will demonstrste the working flow of Git and Github

## Setting up Github Account

1. Go to github.com
2. Signup using a valid gamail account and setup password
3. Explore the options for further setting of your profile

## Setting up Git on your Local machine

1. Download git from https://www.atlassian.com/git/tutorials/install-git (according to your operating system + follow the instruction at the site)
2. For windows select both git bash and command prompt option during the installation process and for other options keep the default
3. Open git bash
4. Run the following command:
   $ git config --global user.name "Your name(may the github user name)"
    $ git config --global user.email "your email(may the email used to signup github)"

## Setting up SSH keys for your git and github account

You can follow the link https://help.github.com/en/github/authenticating-to-github/about-ssh
or you can follow the steps bellow:
(About SSH)
Using the SSH protocol, you can connect and authenticate to remote servers and services.
With SSH keys, you can connect to GitHub without supplying your username or password at each visit.
When you set up SSH, you'll generate an SSH key and add it to the ssh-agent and then add the key to your GitHub account.
Adding the SSH key to the ssh-agent ensures that your SSH key has an extra layer of security through the use of a passphrase.

1. Open Terminal or Git Bash.

Paste the text below, substituting in your GitHub email address.

\$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
This creates a new ssh key, using the provided email as a label.

> Generating public/private rsa key pair.
> When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

> Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]

2.  At the prompt, type a secure passphrase.

    > Enter passphrase (empty for no passphrase): [Type a passphrase]
    > Enter same passphrase again: [Type passphrase again]

3.  Adding your SSH key to the ssh-agent:
    a. Start the ssh-agent in the background.

        $ eval "$(ssh-agent -s)"
        > Agent pid 59566

    b. Add your SSH private key to the ssh-agent.

        $ ssh-add ~/.ssh/id_rsa

4.  Add the SSH key to your GitHub account:
    a. Copy the SSH key to your clipboard:
    \$ clip < ~/.ssh/id_rsa.pub # Copies the contents of the id_rsa.pub file to your clipboard
    b. Go to your github account
    c. In the upper-right corner of any page, click your profile photo, then click Settings.
    d. In the user settings sidebar, click SSH and GPG keys.
    e. Click New SSH key or Add SSH key.
    f. In the "Title" field, add a descriptive label for the new key.
    For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
    g. Paste your key into the "Key" field.
    h. Click Add SSH key.
    i. If prompted, confirm your GitHub password.

## If you want to change the passphrase of your SSH key

You can change the passphrase for an existing private key without regenerating the keypair by typing the following command:

\$ ssh-keygen -p

> Enter file in which the key is (/Users/you/.ssh/id_rsa): [Hit enter]
> Key has comment '/Users/you/.ssh/id_rsa'
> Enter new passphrase (empty for no passphrase): [Type new passphrase]
> Enter same passphrase again: [One more time for luck]
> Your identification has been saved with the new passphrase.

If your key already has a passphrase, you will be prompted to enter it before you can change to a new passphrase.
