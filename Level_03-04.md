# Bandit Level 03 → Level 04

## Objective

The objective is to retrieve the password for Bandit Level 4 from a hidden file located in the inhere directory.

## Initial observations

The inhere directory is present in the home directory.
The password is stored in a hidden file inside this directory.
Hidden files in Linux usually begin with a dot (.).
The normal ls command does not display hidden files.

## Approach

I first listed the files in the home directory using ls and identified the inhere directory.
I then entered the directory using cd inhere. Since the password was stored in a hidden file, I used ls -la to display all files, including hidden ones.
After identifying the hidden file, I used the cat command to read its contents and retrieve the password.

## Commands used

### Connect to Bandit Level 3 
ssh bandit3@bandit.labs.overthewire.org -p 2220 
### List files in the current directory 
ls 
### Enter the inhere directory 
cd inhere 
### List all files, including hidden files 
ls -la 
### Read the hidden file 
cat .hidden

## Explanation

ssh bandit3@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 3 server.
ls: Lists the files and directories in the current directory.
cd inhere: Changes the current working directory to inhere.
ls -la: Displays all files, including hidden files, along with detailed information.
cat .hidden: Displays the contents of the hidden file named .hidden.

## Solution

The password for Bandit Level 4 was successfully retrieved by locating and reading the hidden file .hidden inside the inhere directory.

## Key learnings

Hidden files in Linux begin with a dot (.).
The ls -a command displays hidden files.
The ls -l command provides detailed file information.
The cd command is used to navigate between directories.
Hidden files can be accessed directly by specifying their names.
