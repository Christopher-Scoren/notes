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

`echo` - accepts the string “Hello” as standard input, and echoes the string “Hello” back to the terminal as standard output.
>$ echo "Hello"  
>Hello

`standard input`, abbreviated as stdin, is information inputted into the terminal through the keyboard or input device.  
`standard output`, abbreviated as stdout, is the information outputted after a process is run.  
`standard error`, abbreviated as stderr, is an error message outputted by a failed process.

`>` command redirects the standard output to a file. 
>`$ echo "Hello" > hello.txt`  
>Here, "Hello" is entered as the standard input, and is then redirected to the file hello.txt 

* `>` - takes the standard output of the command on the left, and redirects it to the file on the right.
>`$ cat deserts.txt > forests.txt`
>Here the standard output of cat deserts.txt is redirected to forests.txt.
>> `>` overwrites all original content in forests.txt. When you view the output data by using cat on forests.txt, you will see only the contents of deserts.txt.

`>>` -  takes the standard output of the command on the left and appends (adds) it to the file on the right.
>`$ cat deserts.txt >> forests.txt`  
>Here, the output data of forests.txt will contain the original contents of forests.txt with the content of deserts.txt appended to it.

`<` - takes the standard input from the file on the right and inputs it into the program on the left.
>`$ cat < deserts.txt`  
>Here, deserts.txt is the standard input for the cat command. The standard output appears in the terminal.

`|` - takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.  
>`$ cat volcanoes.txt | wc `  
>cat volcanoes.txt becomes the standard input of wc. in turn, the wc command outputs the number of lines, words, and characters in volcanoes.txt, respectively.

>`$ cat volcanoes.txt | wc | cat > islands.txt`
>Multiple |s can be chained together. Here the standard output of cat volcanoes.txt is “piped” to the wc command. The standard output of wc is then “piped” to cat. Finally, the standard output of cat is redirected to islands.txt.

`sort` -  takes the standard input and orders it alphabetically for the standard output (it doesn’t change the file itself).
>`$ sort continents.txt`

>`$ cat glaciers.txt | sort > sorted-glaciers.txt `  
>Here, the command takes the standard output from cat glaciers.txt and “pipes” it to sort. The standard output of sort is redirected to a new file named sorted-glaciers.txt.

`uniq` -  It filters out adjacent, duplicate lines in a file.  
>`$ uniq deserts.txt `  
>Here uniq deserts.txt filters out duplicates of "Sahara Desert", because its duplicate directly follows the previous instance. The “Kalahari Desert” duplicates are not adjacent, and thus remain.

`grep` - stands for “global regular expression print.” It searches files for lines that match a pattern and then returns the results. It is also case sensitive.  
>`$ grep America continents.txt `  
>grep searched for anything that matched “America” in continents.txt.

* `grep -i` enables the command to be case insensitive.  
>`$ grep -i America continents.txt` - grep searched for capital or lowercase strings that match “America” in continents.txt.

* `grep -R` - searches all files in a directory and outputs filenames and lines containing matched results. -R stands for “recursive”.
```
$ grep -R Arctic /home/ccuser/workspace/geography
/home/ccuser/workspace/geography/deserts.txt:Arctic Desert
/home/ccuser/workspace/geography/oceans.txt:Arctic Ocean
```
* `grep -Rl` searches all files in a directory and outputs only filenames with matched results (so no lines). l (a lowercase L, not a capital i) stands for “files with matches.”

`sed` - stands for “stream editor.” It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to “find and replace.”
>>`sed 's/snow/rain/' forests.txt`  
>`s`: stands for “substitution.” It is always used when using sed for substitution. It will only replace the first instance of “snow” on a line.
>`snow`: the search string, or the text to find.
>`rain`: the replacement string, or the text to add in place  
>>`sed 's/snow/rain/g' forests.txt`
>`g` expression, meaning “global.” - all instances of “snow” on a line will be turned to “rain.”


## Configuring the Environment

`environment` - session with all settings and preferences

`nano` is a command line text editor. 
>`$ nano hello.txt`

commands in nano editor:  
![image](https://user-images.githubusercontent.com/55635400/114768515-a03ab780-9d71-11eb-9d41-50fb159b670b.png)  
`^` = ctrl

* Ctrl + O saves a file. O stands for output.  
* Ctrl + X exits the nano program. X stands for exit.  
* Ctrl + G opens a help menu.

A `bash profile` is a file used to store environment settings for your terminal, and it’s accessible by the name `~/.bash_profile`.  
When a session starts, it loads the contents of the bash profile before executing commands.

* The ~ represents the user’s home directory.  
* The . indicates a hidden file.  

to open a bash profile: `nano ~/.bash_profile`
>When you edit the bash profile, you can add commands to execute every time a new terminal session is started.

`source ~/.bash_profile` - To activate the changes made in ~/.bash_profile for the current session

The `alias` command allows you to create keyboard shortcuts, or aliases, for commonly used commands.

`alias pd="pwd"` -  creates the alias pd for the pwd command, which is then saved in the bash profile.  
>`alias ll="ls -la"` and `alias hy="history"`

`Environment variables` are variables that can be used across commands and programs and hold information about the environment.
>`export USER="Jane Doe"`  
>>The line USER="Jane Doe" sets the environment variable USER to a name “Jane Doe”. Usually the USER variable is set to the name of the computer’s owner.  
>>The line export makes the variable to be available to all child sessions initiated from the session you are in. This is a way to make the variable persist across programs.  
>>At the command line, the command echo $USER returns the value of the variable. Note that $ is always used when returning a variable’s value. Here, the command echo $USER returns the name set for the variable.

`PS1` is an environment variable that defines the makeup and style of the command prompt.  
>`export PS1=">> "`  
>>export PS1=">> " sets the command prompt variable and exports the variable. Here we change the default command prompt from $ to >>.  
>>After using the source command, the command line displays the new command prompt.

The `HOME` variable is an environment variable that displays the path of the home directory ~.
>`$ echo $HOME`




