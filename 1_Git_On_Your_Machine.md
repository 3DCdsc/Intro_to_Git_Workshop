# Intro_to_Git_Workshop

## Session 1

This is an introductory workshop to Git, created by 3DC. This Readme contains the lesson content for this workshop, including sample snippets.

1. [What is Git and why should I learn Git?](#what-is-git-and-why-should-i-learn-git)
2. [What is GitHub and how is it different from Git?](#what-is-github-and-how-is-it-different-from-git)
3. [Installation (Git)](#installation-git)
   1. [Windows](#windows)
   2. [Mac OS X](#mac-os-x)
   3. [Linux (Ubuntu/Debian)](#linux-ubuntudebian)
   4. [Linux (Fedora)](#linux-fedora)
4. [Environment Setup](#environment-setup)
   1. [Credentials](#credentials)
5. [Creating your first Git Repository](#creating-your-first-git-repository)
6. [Checking the status of your Git Repository](#checking-the-status-of-your-git-repository)
7. [Adding files to your Git Repository](#adding-files-to-your-git-repository)
8. [Staging, Committing and pushing Changes](#staging-committing-and-pushing-changes)
9. [Viewing the committed History](#viewing-the-committed-history)
10. [Removing a File](#removing-a-file)
15. [Branching](#branching)
16. [Merges](#merges)
   1. [Preparing to Merge](#preparing-to-merge)
   2. [Merging](#merging)
17. [Fast Forward Merge](#fast-forward-merge)
   1. [3-Way Merge](#3-way-merge)
   2. [Resolving Merge Conflicts](#resolving-merge-conflicts)

## What is Git and why should I learn Git?  

<div style="text-align:center"><img src="imgs/git.png" /></div>

Git is a version control tool. It helps you to manage the project history of modern projects (usually software). It is almost always an essential tool when collaborating with others on software projects.

Modern projects are usually iteratively improved, and Git helps us to manage these small iterations efficiently and cleanly.

## What is GitHub and how is it different from Git?

<div style="text-align:center"><img src="imgs/github.png" /></div>

Github is a popular Git repository hosting service. A Git repository is a virtual Git collection, containing different versions of your project files. You can find many Git repositories on Github's website (www.github.com)

We will first start with the fundamentals of Git.

## Installation (Git)

### Windows

You will need to install [Git Bash for Windows](https://git-scm.com/download/win). Just follow the installation instructions and choose the default settings for now.

### Mac OS X

If it is not already installed, use the following command in Terminal

```terminal
brew install git
```

### Linux (Ubuntu/Debian)

If it is not already installed, use the following command in bash

```bash
sudo apt-get install git
```

### Linux (Fedora)

If it is not already installed, use the following command in bash

```bash
sudo yum install git
```

## Environment Setup

From now onwards, the commands used in this tutorial will be done in a terminal window (Windows: Git Bash, Mac OS X: Terminal, Linux: Bash)

### Credentials

Let's set up your name and email address. This information is used to identify you whilst you are making changes to your project.

```bash
git config --global user.name "Your name here"
git config --global user.email youremail@email.com
```

## Creating your first Git Repository

Recall a Git repository is a virtual Git collection, containing different versions of your project files. This git repository can reside inside a local folder inside your computer, and it can also be linked to a remote repository on somewhere like Github. (This concept is somewhat similar to a file-hosting website like Dropbox)

For now, we shall start by creating a local Git repository.
1. Navigate to a local location in your computer
2. Create an empty folder for your repository.
3. Open the folder in your Git Bash/Terminal (Hint: Right Click inside your empty folder, select `Open in Git Bash` or `Open in Terminal`)
4. Use the following command to initalise a git repository inside this folder

```bash
git init
```

You should see a message acknowledging the creation of the git repository.
![](imgs/ss-gitinit.png)

## Checking the status of your Git Repository

To check the status of your Git repository (as a sanity check or whatever), you can use the following command. This command also checks that the git repository has been initialised.

```bash
git status
```

You should see something like this:

![](imgs/ss-gitstatus.png)

You will understand meaning of the messages later.

## Adding files to your Git Repository

[Download](https://github.com/kaypohleb/js-teaching) the following files, which contains a template for a personal website, and place them inside your folder with the git repository.

While the files are already in the folder (**working directory**), they have not yet been "added" to the **repository** per say, you need to **manually add** these files into the repository using git commands.

You can confirm this by using `git status` to check. You will see something like this:

![](insert some img here)

You will find the files listed under **untracked files**.

## Staging, Committing and pushing Changes

![](imgs/stagingarea.png)

- The **staging area** can be thought of as the intermediary between your folder (working directory) and the git repository. In the staging area, you decide and **mark** which files that you have added/modified/removed should be updated into the git repository.

The ```git add``` command is used to add changes in the working directory to the staging area. It is used to tell Git that you would like to include updates to a particular file in the next commit. However, ```git add``` does not actually record any change until you run the ```git commit```command

Let us take a closer look on how these commands actually work!

First, you need to edit your files in your working directory. Once you have done that and you are ready to save a copy of your project, you stage the changes using the ```git add``` command. Once you are happy with this staged snapshot, you can commit it to the project history using ```git commit```. The ```git reset``` command can be used to undo a commit or a staged snapshot.

In a Git project timeline, commits are like the core building blocks! They can be thought of as milestones along the timeline of a Git project. Git snapshots are always committed to the local repository. Each developer's local repository acts as the buffer between their contributions and the central repository.

<div style="text-align:center"><img src="images/git-add.png" /></div>

Here are some common options:

```bash
git add <file>
```
this allows you to stage all changes in your file for the next commit

```bash
git add <directory>
```
this allows you to stage all changes in your directory for the next commit

```bash
git commit
```
this allows you to commit the staged snapshot. Once this command is run you will be prompted to type in the description of the commit using a text editor

```bash
git commit -a
```
this allows you to commit a snapshot of the changes done in the whole working directory

```bash
git commit -m "<message>"
```
this allows you set the description along with the commit function

```bash
git commit -am "<message>"
```
this command allows you to combine the -a and the -m options

we will now see how you can use these commands to commit the changes you made to your personal blog!


## Viewing the committed History

The ```git log``` command shows you all the committed snapshots. It is used to list and filter the project history and to search for any particular changes

The log output can be personalized differently by allowing you to filter commits and to display them in an entirely user-defined format

<div style="text-align:center"><img src="images/git-log" /></div>

```bash
git log
```
this command allows you to view the entire commit history. It uses space for scrolling and q for exiting if the log output takes up multiple screens

```bash
git log --oneline
```
this command allows you to fit each commit into a single line, which comes in handy when you would like to get an overview of the project history

these are just some of the most commonly used commands, to see the full list of available formatting options use the ```git help log``` command to see the man page for the Git Log tool. Alternatively you could view the [online documentation](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History) here!

## Removing a File

As your project changes over time, there will be times when you would have to remove a file or an entire directory from a repository. Git has a special command to remove files, which also takes some important flags depending on your use-case!

Let us now take a look at the ```git rm``` command and how it can be used to remove files and directories from your repository!

```bash
git rm <filename>
```
this command can be used to remove a single file from the repository

```bash
git rm <filename1> <filename2>
```
this command can be used to remove multiple files

```bash
git rm -r <directory>
```
this command can be used to remove an entire directory from the repository

However we are not quite done yet! If you run the ```status``` command you will notice that the removal of the file is still in staging and needs to be committed to the repository.


## Branching

Git branches are essentially a pointer to a snapshot of your changes! It is good practice to spawn a branch everytime you want to add a new feature or fix a bug to encapsulate your changes. By doing so the chances of unstable code being merged into the main code base will become lesser.

<div style="text-align:center"><img src="images/branching.png" /></div>

In this image, the repository contains two isolated lines of development of a little feature and a longer running feature. You can thus visualize how through branching developers can not only work on the two features simulataneouly but can also be rest assured that the master branch is kept free from possibly unstable code.

Do note that the master branch is the name of the default branch. In this picture the central line of development depicts the master branch.

How this works is that Git stores a branch as a reference to a commit. In other words, a branch represents the tip of a series of commits and is not a container of for commits.

Let us know take a look at some of the common options in branching

```bash
git branch
```
This command lists all the branches in your repository

```bash
git branch <branch>
```
this command creates a new branch named ```<branch>```

```bash
git branch -d <branch>
```
this command allows you to delete the specified branch

## Merges

The ```git merge``` command is essentially used to take two independent lines of development created by ```git branch``` and integrate them into a single branch. Let us take a closer look on how this works:

The ```git merge``` commit will combine multiple sequences of commits into one unified history. We will now focus on the merging of two branches even though this concept can be extended to include more than two branches. What ```git merge``` does is it takes two commit pointers (Generally the tip) and finds a common base commit between them so that it can create a new "merge commit" that combines the changes of each queued merge commit sequence.

<div style="text-align:center"><img src="images/Branch-1.png" /></div>
<div style="text-align:center"><img src="images/Branch-2.png" /></div>

Here is a pictorial representation of how this is done!

### Preparing to Merge

There are a couple things you need to take care of to ensure that the merge goes smoothly:

1) Confirming the receiving branch: Execute ```git status``` to ensure that the``` HEAD``` is pointed to the correct merge-receiving branch
2) Making sure that the receiving branch and the merging branch are up-to-date with the latest remote changes

### Merging

Once you are ready to merge, execute the ``` git merge <branchname>``` command to merge ```<branchname>``` to the receiving branch

## Fast Forward Merge

This occurs when there is a linear path from the current branch tip to the target branch. In such a situation what Git needs to do is to "Fast Forward" the current branch tip to the target branch. What this essentially does is combining the histories of the two branches.

<div style="text-align:center"><img src="images/fast-forward.jpg" /></div>

Here is a pictorial depiction of how a fast forward merge works

### 3-Way Merge

When there exists no linear path between the two branches (The branches are merged) then the only option the Git has is to combine them via a 3-Way merge. 3-Way merges use a dedicated commit to tie together the two histories. The nomenclature comes from the fact that Git uses three commits to generate the merge commit: the two branch tips and their common ancestor.

The merging diagram we presented to you earlier shows how 3-Way merging is carried out!

### Resolving Merge Conflicts

Sometimes two developers will change the same line of code in two different ways and in such a case, Git can't tell which version is correct. Since that is something that only a developer can tell, merge conflicts must be resolved manually.

If this happens you should see something like this in your screen

```bash
Auto-merging <file>
CONFLICT (content): Merge conflict in <file>
Automatic merge failed; fix conflicts and then commit the result.
```
Once you open the open the file in which there is a conflict you should see something like this:

```
<<<<<<< HEAD
This is an edit on the master branch
=======
This is an edit on the <branch-name> branch
>>>>>>> <branch-name>

```

The "<<" charecters denotes the current branch's edits and the "==" sign denotes the end of the first section. The second section is where the edits are from the attempted merge, and it starts with the "==" signs and ends with the ">>" signs.

Since you are the developer, you get to decide what stays and what goes. Make your edits as required and then close the file. Once you are done with this follow the directions to add the files and then commit.

You can find advanced information on Git merging and merge-conflict resolution [right here](https://git-scm.com/book/en/v2/Git-Tools-Advanced-Merging).
