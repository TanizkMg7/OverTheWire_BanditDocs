# Bandit Level 07→ Level 08

## Objective

The objective is to retrieve the password for Bandit Level 8 from a file named data.txt.

The password is located next to the word millionth.

## Initial observations

The file data.txt is present in the home directory.
The file contains many lines of text.
Searching through the entire file manually would be inefficient.
The grep command can be used to search for a specific word or pattern within a file.

## Approach

I first inspected the contents of the home directory and found data.txt.

Instead of manually searching through the large file, I used grep to search for the word millionth.

The output showed the word millionth followed by the password for the next level.

## Commands used

### #Connect to Bandit Level 7 
ssh bandit7@bandit.labs.overthewire.org -p 2220 
### #List the files in the current directory 
ls 
### #Search for the word "millionth" in data.txt 
grep "millionth" data.txt

## Explanation

ssh bandit7@bandit.labs.overthewire.org -p 2220: Connects to the Bandit Level 7 server.
ls: Lists the files in the current directory.
grep "millionth" data.txt: Searches data.txt for lines containing the word millionth.

grep is particularly useful when dealing with large amounts of text because it allows specific patterns or words to be located quickly without manually reading the entire file.
## Solution

The command:

grep "millionth" data.txt

returned the line containing millionth and the password for Bandit Level 8.

## Key learnings

grep is used to search text for specific patterns.
Searching with grep is much more efficient than manually inspecting a large file.
Linux command-line tools can be combined with files to quickly locate relevant information.
Text searching is a fundamental technique in Linux and cybersecurity.
