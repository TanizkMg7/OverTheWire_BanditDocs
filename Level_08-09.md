# Bandit Level 08 → Level 09

## Objective

The objective is to retrieve the password for Bandit Level 9 from the file data.txt.

The password is the only line in the file that occurs exactly once.

## Initial observations

The file data.txt contains many lines.
Most lines are repeated.
The required password occurs only once.
The sort and uniq commands can be combined to identify lines that occur only once.

## Approach

I first used sort to arrange all the lines in data.txt in alphabetical order.

I then piped the output to uniq -u. The -u option displays only lines that occur exactly once.

The resulting line was the password for Bandit Level 9.
## Commands used
### #Connect to Bandit Level 8 
ssh bandit8@bandit.labs.overthewire.org -p 2220 
### #Find the line that occurs only once 
sort data.txt | uniq -u
## Explanation

sort data.txt: Sorts all lines in data.txt alphabetically.
|: The pipe operator passes the output of one command as input to another command.
uniq -u: Displays only lines that occur exactly once.

uniq detects repeated lines only when they are next to each other. Therefore, sort is used first to place identical lines together.
## Solution

The command:

sort data.txt | uniq -u

returned the single line that occurs only once in the file.

That line is the password required to log in to Bandit Level 9.

## Key learnings

sort arranges lines in a specific order.
uniq is used to detect or remove consecutive duplicate lines.
uniq -u displays only unique lines.
The pipe (|) allows the output of one command to become the input of another.
Combining simple Linux commands can efficiently solve text-processing problems.
