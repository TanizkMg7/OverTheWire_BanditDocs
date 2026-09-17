# Bandit Level 02 → Level 03

## Objective

The objective is to retrieve the password for Bandit Level 3 from a file named spaces in this filename located in the home directory.

## Initial observations

The objective is to retrieve the password for Bandit Level 3 from a file named spaces in this filename located in the home directory.

## Approach

I first listed the files in the home directory using ls and identified the file named spaces in this filename.
To read the file, I enclosed its name in double quotes. This ensures that the spaces are treated as part of the filename rather than as separators between multiple arguments.

## Commands used

### Connect to Bandit Level 2 
ssh bandit2@bandit.labs.overthewire.org -p 2220 
### List files in the current directory 
ls 
### Read the file containing spaces in its name 
cat "spaces in this filename"

## Explanation

ssh bandit2@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 2 server.
ls: Lists the files in the current directory.
cat "spaces in this filename": Displays the contents of the file.
Double quotes (" ") preserve the spaces within the filename and pass it as a single argument to cat.

## Solution

The password for Bandit Level 3 was successfully retrieved by reading the file named spaces in this filename.

## Key learnings

Spaces in filenames must be handled carefully in the Linux shell.
Double quotes can group a filename containing spaces into a single argument.
Backslash (\) can be used to escape spaces.
Shell argument parsing is important when working with files and command-line utilities.
