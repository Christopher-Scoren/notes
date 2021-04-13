# Content:

1. [Intro](#Introduction)
2. [Navigating the File System](#Navigating-the-File-System)
3. [Viewing and changing the file system](#Viewing-and-changing-the-file-system)
4. [Redirecting Input and Output](#Redirecting-Input-and-Output)
5. [Configuring the Environment](#Configuring-the-Environment)

## Introduction

The `command line` is a text interface for the computer’s operating system. You can use it to traverse and edit your computer’s filesystem. Through the command line, you can create new files, edit the contents of those files, delete files, and more.

 A `command` is a directive to the computer to perform a specific task.
 `$` - shell prompt

Command line is text-based. It doesn't have a graphical interface
![image](https://user-images.githubusercontent.com/55635400/114563579-34c0ef00-9c78-11eb-8834-0948c81f91d7.png)

`Bash`, or `the Bourne-Again SHell`, is a CLI that was created in 1989 by Brian Fox as a free software replacement for the Bourne Shell.  
A `shell` is a specific kind of CLI. 

## Navigating the File System

A filesystem organizes a computer’s files and directories into a tree structure

* The first directory in the filesystem is the root directory. It is the parent of all other directories and files in the filesystem.
* Each parent directory can contain more child directories and files.

### Commands  
`ls` - “lists” all the files and directories inside of the directory  
`pwd` - print working directory  
`cd` - change directory  
> `$ cd 2015` When a file, directory, or program is passed into a command, it is called an argument. Here the 2015 directory is an argument for the cd command.  
> `$ cd jan/memory` - to avoid writing cd twice  
> `cd ..` - to move up

`mkdir` - making directories (folders)
> `$ mkdir media` || `$ mkdir media/tv` - to create a dir when you are 1 level upper

`touch` - creates a new file inside the working directory
> `$ touch keyboard.txt`

### Helper commands
`clear` - clear your terminal It doesn’t change or undo your previous commands, it just clears them from the view. To see them you need to scroll up.  
`tab` - to autocomplete your command. When you are typing the name of an existing file or directory, you can use tab to finish the rest of the name.  
`↑` and `↓` - to cycle through your previous commands.


## Viewing and changing the file system

`Options` modify the behavior of commands.

`ls -a` - displays all the files and directories, including those starting with a dot (.)  

* more for ls:  
 * `-a` - lists all contents, including hidden files and directories  
 * `-l` - lists all contents of a directory in long format, as well as the file permissions  
 * `-t` - orders files and directories by the time they were last modified.

* `ls -l`
>drwxr-xr-x 5  cc  eng  4096 Jun 24 16:51  action  
drwxr-xr-x 4  cc  eng  4096 Jun 24 16:51  comedy  
drwxr-xr-x 6  cc  eng  4096 Jun 24 16:51  drama  
-rw-r--r-- 1  cc  eng     0 Jun 24 16:51  genres.txt  
>> Here’s what each column means:
>> 1. Access rights. These indicate the read, write, and execute permissions on the file or directory allowed to the owner, the group, and all users. You can read more about file permissions.  
>> 2. Number of hard links. This number counts the number of child directories and files. This number includes the parent directory link (..) and current directory link (.).  
>> 3. The username of the file’s owner. Here the username is cc.  
>> 4. The name of the group that owns the file. Here the group name is eng.  
>> 5. The size of the file in bytes.  
>> 6. The date & time that the file was last modified.  
>> 7. The name of the file or directory.  

Multiple options can be used together, like `ls -alt`.

`cat` - outputs the contents of a specified file. 
> `cat action/superwoman.txt`

`cp` - copies files or directories.
> `cp source.txt destination.txt` or `cp source.txt destination/`
> To copy multiple files into a directory, use cp with a list of source files as the first arguments, and the destination directory as the last argument: `cp file1.txt file2.txt my_directory/`

`wildcards` - special characters like * to select groups of files  
`*` - `cp * my_directory/` - to copy all files in the current working directory into another directory.  
`cp w*.txt my_directory/`  - selects all files in the working directory starting with “w” (prefix) and ending with “.txt” (suffix), and copies them to my_directory/.

`mv` - moves files 
>`mv my_file.txt my_directory/` or `mv my_file_1.txt my_file_2.txt my_directory/` - to move one or several files
>`mv file_origin.txt file_renamed.txt` - to rename a file

`rm` - deletes files and directories
>`rm unwanted_file.txt`
* `-r` -  stands for “recursive,” and it’s used to delete a directory and all of its child directories.

## Redirecting Input and Output



## Configuring the Environment
