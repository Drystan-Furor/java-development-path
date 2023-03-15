---
title: "Git repo setup"
date: 2022-12-16 20:01:01 +0100
categories: [Tools, git]
tags: [git repo setup]     # TAG names should always be lowercase
---

# GIT start repo

## How to start a repository on command line

To start a repository on the command line, you can follow these steps:

1. Open your terminal or command prompt.
2. Navigate to the directory where you want to create the repository.
3. Run the command `git init`. This will initialize an empty Git repository in the current directory.
4. Add files to the repository by creating or copying them into the repository directory.
5. Run the command `git add .` to add all files in the directory to the staging area. Alternatively, you can specify
   individual files to add by replacing the . with the file name.
6. Commit the changes to the repository by running the command `git commit -m "Initial commit"`. This will create a new
   commit with the changes you added in the previous step.

Your repository is now created and you can start working with Git to manage your code changes. You may also need to
connect your local repository to a remote repository if you want to share your code with others or collaborate with a
team.

***

## How to connect your local repository to a remote repository

To connect your local repository to a remote repository, you can follow these steps:

1. Create a new repository on your remote hosting service, such as GitHub or GitLab.
2. Copy the URL of the remote repository. This will usually be found on the repository's main page.
3. In your local repository, run the command `git remote add origin <remote repository URL>`. This will create a new
   remote called "origin" that points to your remote repository.
4. Verify that the remote has been added by running the command `git remote -v`. This will show you a list of all the
   remotes that your local repository is connected to.
5. Push your local repository to the remote repository by running the command `git push -u origin master`. This will
   upload all the commits in your local repository to the remote repository.

Your local repository is now connected to the remote repository, and you can use Git to push and pull changes between
the two repositories.

***

## How to set up a mac with an ssh for github to work from command line

To set up your Mac with SSH for GitHub to work from the command line, follow these steps:

### 1. Check if you already have an SSH key on your Mac by running the following command in your terminal:

```
ls -al ~/.ssh
```

> If you have an SSH key, you should see two files named id_rsa and id_rsa.pub. If you don't see these files, move on to
> the next step.

### 2. Generate a new SSH key by running the following command in your terminal:

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

> This command will generate a new SSH key with a 4096-bit RSA encryption and the email address you provide.

### 3. When you're prompted to "Enter a file in which to save the key," press Enter to accept the default file location.

### 4. When you're prompted to "Enter a passphrase," you can either create a passphrase or leave it blank. If you create a passphrase, you'll need to enter it every time you use your SSH key.

### 5. Start the ssh-agent by running the following command in your terminal:

```
eval "$(ssh-agent -s)"
```

> This command will start the ssh-agent, which is a background process that manages your SSH keys.

### 6. Add your SSH key to the ssh-agent by running the following command in your terminal:

```
ssh-add ~/.ssh/id_rsa
```

### 7. Copy your public SSH key to your clipboard by running the following command in your terminal:

```
pbcopy < ~/.ssh/id_rsa.pub
```

> This command will copy your public SSH key to your clipboard.

### 8. Go to your GitHub account settings and click on "SSH and GPG keys" in the left sidebar.

   	Click on the "New SSH key" button.

   	Give your SSH key a title and paste your public SSH key into the "Key" field.

   	Click on the "Add SSH key" button.

### 9. Now you should be able to use Git and GitHub from the command line on your Mac using SSH. To test it, run the
   following command in your terminal:

```
ssh -T git@github.com
```

You should see a message that
says  ```"Hi {your GitHub username}! You've successfully authenticated, but GitHub does not provide shell access." ```If
you see this message, you're all set up and ready to go!

***

## ERROR

```
git push -u origin master
Username for 'https://github.com': <your username>>
Password for 'https://<your username>>@github.com':
fatal: unable to access 'https://github.com/<your username>>/<your repo name>>.git/': The requested URL returned error: 400
```

The error message you're seeing suggests that there's an issue with the URL you're using to push your changes to GitHub.
The error message specifically says "The requested URL returned error: 400", which means that the server was unable to
understand the request you made.

One potential issue is that you're using the "https" URL for your remote repository instead of the "ssh" URL. Using
the "ssh" URL can be more secure and can avoid some authentication issues.

To update your remote URL to use the "ssh" URL, you can run the following command:

```
git remote set-url origin git@github.com:D<your username>>/<repo name >>.git
```

> This command sets the URL of the remote named "origin" to the "ssh" URL for your repository.

Once you've updated the remote URL, you can try pushing your changes again using the command:

```
git push -u origin master
```

You should be prompted for your SSH key passphrase (if you set one up). After entering your passphrase, your changes
should be pushed to GitHub.


***
> Start daily exercises [in the Code Gym](https://codegym.cc/)
> {: .prompt-tip }

# [Start with: Start your journey to become a Java Developer]({% link _posts/2022-12-01-start.md %})

# [Continue with: Spring]({% link _posts/2022-12-08-spring.md %})
