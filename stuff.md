# Intro_to_Git_Workshop

## Git Commands

We will now be going over some basic git commands

### git add

This command is used to add changes in the working directory to the staging area. It is used to tell Git that you would like to include updates to a particular file in the next commit. However, ```git add``` does not actually record any change until you run the ```git commit```command, which we will look into soon!!

Let us take a closer look on how ```git add``` actually works!

First, you need to edit your files in your working directory. Once you have done that and you are ready to save a copy of your project in its current stage, you stage the changes using the ```git add``` command. Once you are happy with this staged snapshot, you can commit it to the project history using ```git commit```. The ```git reset``` command can be used to undo a commit or a staged snapshot.

in addition to these two commands, a third command ```git push``` is necessary for a complete collaborative Git workflow. This is used to send changes to remote repositories for collaboration by allowing other team members to get access to a set of saved changes.

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
  
![](insert screenshots with explanation below)




