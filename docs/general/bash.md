# BASH

- [What is a command line interface?](#what-is-a-command-line-interface?)
- [Commands](#commands)
- [Redirection](#redirection)
- [Bash Profile](#bash-profile)
- [Bash Scripting](#bash-scripting)

## What is a command line interface?

- A command line interface (CLI) is a means of interacting with a computer using text commands. Users write out commands to make their computers carry out the desired tasks. Constrast this to graphical user interface (GUI); Whenever you interact with your computer with a mouse or your mobile device with your fingers, you're doing so using visual cues provided by a GUI.

## Commands

- **pwd**: print working directory
- **ls**: list files and directories
  - **ls -a**: list all files including files and directories that start with a dot. Files starting a dot are hidden.
  - **ls -l**: lists all contents of a directory in long format
    - Access Right / Number of Hard Links / Username / Group Name / Size / Date & Time Modified / Name
  - **ls -t**: order files and directories by the time they were last modified
  - **ls -alt**: combination of -a -l -t
- **touch**: create a new file
- **mkdir**: creates a directory
- **cp**: copies a file into a directory or file content to another file
- **mv**: moves file into a directory or rename file
- **rm**: deletes file or directories -**rm -r**: the r stands for recursive, used to delete directory and all of its child directories and files
- **cat**: outputs the contents of a file to the terminal
- **less**: similar to cat but better at handling larger files, it displays files in the terminalone page at a time
- **nano**: is a command line text editor
- **history**: shows user command history in current session
- **clear**: clear terminal text

## Redirection

- **>**: redirection, takes the standard output of the command on the left, and redirects it to the file on the right.
- **>>** takes the standard output of the command on the left and appends (adds) it to the file on the right
- **|**: is a “pipe”. The | takes the standard output of the command on the left, and pipes it as standard input to the command on the right.
- **wc**: command outputs the number of lines, words, and characters
- **sort**: takes the standard input and orders it alphabetically for the standard output
- **uniq**: stands for “unique” and filters out adjacent, duplicate lines in a file
- **grep**: stands for “global regular expression print”. It searches files for lines that match a pattern and returns the results.
  - **grep -i**: enables the command to be case insensitive
  - **grep -R**: searches all files in a directory and outputs filenames and lines containing matched results
  - **grep -Rl**: searches all files in a directory and outputs only filenames with matched results
- **sed**: stands for “stream editor”. It accepts standard input and modifies it based on an expression, before displaying it as output data.
  - sed ' "s" stands for substitution / the search string / the replacement string / ["g" stands for globally without this only substitute first instance]'

## Bash Profile

- **source ~/.bash_profile**: makes the changes in bash_profile settings available right away in the session we are in
- **alias**: the alias command allows you to create keyboard shortcuts, or aliases, for commonly used commands
- **export USER="Jane Doe"**: creates an environment variable
  - to use environment variable, \$USER
- **PS1**: is a variable that defines the makeup and style of the command prompt
- **\$PATH**: is an environment variable that stores a list of directories separated by a colon
  - Each directory contains scripts for the command line to execute. The PATH variable simply lists which directories contain scripts
- **env**: command stands for “environment”, and returns a list of the environment variables for the current user
- **HOME**: is the home directory. It is usually not customized
- **USER**: is the name of the current user

## Bash Scripting

- **Configuration**

  - **~/bin/**: When saving the script file, it is good practice to place commonly used scripts in the ~/bin/ directory
  - **chmod +x script.sh**: The script files also need to have the “execute” permission to allow them to be run
  - To ensure that scripts in ~/bin/ are available, you must add this directory to your PATH within your configuration file:
    - **PATH=~/bin:\$PATH**
    - Now any scripts in the ~/bin directory can be run from anywhere by typing the filename.
  - **#!/bin/bash**: first line of script to make sure script only runs on bash

- **variable="value"**: to set a variable
- **\$variable**: access the value of the variable
- **script.sh 'argument 1' 'argument 2'**: input arguments can be passed to a bash script after the script name, separated by spaces. To access argument in script, $1 $2
- **read (variable)**: can request user input and store in variable
- **read -a bar <<< \$foo**: splits a string into an array
- **Equal**: -eq
- **Not equal**: -ne
- **Less than or equal**: -le
- **Less than**: -lt
- **Greater than or equal**: -ge
- **Greater than**: -gt
- **Is null**: -z
- **Equal**: ==
- **Not equal**: !=

```bash
  if [$index -lt 5]
  then
    echo $index
  else
    echo 5
  fi
```

- **if statements**
  - When comparing strings, it is best practice to put the variable into quotes (")

```bash
for word in $paragraph
do
  echo $word
done
```

- **for loops**
  - Note that word is being “defined” at the top of the for loop so there is no $ prepended. Remember that we prepend the $ when accessing the value of the variable.

```bash
while [ $index -lt 5 ]
do
  echo $index
  index=$((index + 1))
done
```

` **while loops**

- keep looping while the provided condition is true

```bash
until [ $index -eq 5 ]
  do echo $index
  index=$((index + 1))
done
```

- **until loops**

  - loops until the condition is true

## Definitions

- **standard input**: abbreviated as stdin, is information inputted into the terminal through the keyboard or input device
- **standard output**: abbreviated stdout, is the information outputted after a process is run
- **standard error**: abbreviated stderr, is an error message outputted by a failed process
- **redirection**: reroutes standard input, standard output, and standard error
- **~/.bash_profile**: is the name of file used to store environment settings. It is commonly called the “bash profile”. When a session starts, it will load the contents of the bash profile before executing commands
  - **~** represents the user’s home directory
- **environment**: refers to the preferences and settings of the current user
- **environment variables**: are variables that can be used across commands and programs and hold information about the environment.
