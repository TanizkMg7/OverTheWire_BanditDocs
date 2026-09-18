# Bandit Level 04 → Level 05

## Objective

The objective is to retrieve the password for Bandit Level 5 from the only human-readable file in the inhere directory.

## Initial observations

The inhere directory contains several files.
Most of the files contain non-human-readable data.
The password is stored in the only human-readable file.
The file command can be used to determine the type of data contained in each file.

## Approach

I first entered the inhere directory and listed its contents.

Since there were multiple files and their names alone did not indicate which one contained readable text, I used the file command with a wildcard (*) to check the type of every file.

After identifying the file that contained ASCII text, I used cat to display its contents and retrieve the password.

## Commands used

### Connect to Bandit Level 4 
ssh bandit4@bandit.labs.overthewire.org -p 2220 
### Enter the inhere directory 
cd inhere 
### List the files 
ls 
### Check the type of every file 
file ./* 
### Read the human-readable file 
cat ./-file07

## Explanation

ssh bandit4@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 4 server.
cd inhere: Moves into the inhere directory.
ls: Lists the files present in the directory.
file ./*: Uses the file command to determine the type of every file in the directory.
cat ./-file07: Displays the contents of the identified human-readable file.

The * is a wildcard that matches multiple filenames. 
The ./ ensures that filenames beginning with - are treated as filenames rather than command-line options.

## Solution

The password for Bandit Level 5 was found in the only human-readable file, -file07.

## Key learnings

The file command can be used to identify the type of a file.
Wildcards such as * can be used to work with multiple files at once.
Not all files containing useful information are necessarily plain text.
Prefixing filenames with ./ is useful when filenames begin with -.
Identifying file types can help narrow down files during security investigations.
