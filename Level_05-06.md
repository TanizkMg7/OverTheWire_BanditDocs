# Bandit Level 06 → Level 07

## Objective

The objective is to retrieve the password for Bandit Level 6 from a file somewhere under the inhere directory that satisfies the following conditions:

Human-readable
Exactly 1033 bytes in size
Not executable

## Initial observations

The inhere directory contains multiple subdirectories and files.
Manually checking every file would be inefficient.
The find command can search recursively through directories and filter files based on properties such as size, permissions, and type.

## Approach

I first entered the inhere directory and inspected its contents.

Since the required file had specific properties, I used the find command to search recursively for a regular file with a size of exactly 1033 bytes.

I then checked the resulting file to confirm that it was human-readable and not executable. After identifying the correct file, I used cat to read its contents and obtain the password.

## Commands used

### Connect to Bandit Level 5
ssh bandit5@bandit.labs.overthewire.org -p 2220 
### Enter the inhere directory 
cd inhere 
### Find a file with exactly 1033 bytes 
find . -type f -size 1033c # Check the identified file file ./maybehere07/.file2 
### Read the file 
cat ./maybehere07/.file2

## Explanation

ssh bandit5@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 5 server.

cd inhere: Moves into the directory containing the files to be searched.

find .: Starts searching from the current directory.

-type f: Restricts the search to regular files.

-size 1033c: Searches for files whose size is exactly 1033 bytes. The c specifies bytes.

file: Identifies the type and properties of the selected file.

cat: Displays the contents of the file.

## Solution

The required file was identified by searching for a regular file with exactly 1033 bytes.

After confirming that the file was human-readable and non-executable, its contents were displayed using cat.

## Key learnings

find can recursively search through directories.

find can filter files based on properties such as type and size.

The -type f option searches only for regular files.

The -size 1033c option searches for files exactly 1033 bytes in size.

The file command can be used to verify a file's type.

File permissions and properties can be useful clues when searching for specific files.
