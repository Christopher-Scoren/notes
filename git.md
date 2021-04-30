# Content

1. Intro
  1. git workflow
  2. 


# Introduction

`git init` - init = initialize The command sets up all the tools Git needs to begin tracking changes made to the project.

## git workflow

 A Git project can be thought of as having three parts:

1. A `Working Directory`: where you’ll be doing all the work: creating, editing, deleting and organizing files  
2. A `Staging Area`: where you’ll list changes you make to the working directory  
3. A `Repository`: where Git permanently stores those changes as different versions of the project  

The Git workflow consists of editing files in the working directory, adding files to the staging area, and saving changes to a Git repository. In Git, we save changes with a commit

`git status` - to check the status of the changes

In order for Git to start tracking scene-1.txt, the file needs to be added to the staging area.

`git add filename` - add a file to the staging area

`git diff filename` - check the differences between the working directory and the staging area

`git commit -m "Complete first line of dialogue"` - to commit changes (`-m` means message, it has to be quoted)

Standard Conventions for Commit Messages:

* Must be in quotation marks  
* Written in the present tense  
* Should be brief (50 characters or less) when using -m  

`git log` - to view chronology of commitments

![image](https://user-images.githubusercontent.com/55635400/116733221-809fc200-a9f4-11eb-9c12-14bd7bf8b402.png)  
A 40-character code, called a SHA, that uniquely identifies the commit.
