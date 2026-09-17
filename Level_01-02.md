# Bandit Level 01 → Level 02

## Objective

The objective is to retrieve the password for Bandit Level 2 from a file named - located in the home directory.

## Initial observations

The file containing the password is named -.
The hyphen (-) is commonly interpreted by Linux commands as an option or standard input.
Using cat - directly may cause the command to wait for input from the keyboard instead of reading the file.

## Approach

I first listed the files in the home directory using ls and identified the file named -.

To read the file correctly, I specified its path using ./-. The ./ indicates the current directory, allowing cat to interpret the hyphen as a filename rather than an option.

## Commands used

### Connect to Bandit Level 1 
ssh bandit1@bandit.labs.overthewire.org -p 2220 
### List files in the current directory 
ls 
### Read the file named "-" 
cat ./-

## Explanation

ssh bandit1@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 1 server.
ls: Lists the files in the current directory.
cat ./-: Displays the contents of the file named -.
./: Represents the current directory and removes ambiguity between a filename and a command-line option.

## Solution

The password for Bandit Level 2 was successfully retrieved by reading the file named - using:

## Key learnings

Linux commands may interpret filenames beginning with - as options.
Prefixing a filename with ./ helps distinguish it from an option.
The cat command can read files with unusual filenames.
Understanding command-line argument parsing is useful when working with Linux systems.
