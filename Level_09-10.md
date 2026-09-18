# Bandit Level 09 → Level 10

## Objective

The objective is to retrieve the password for Bandit Level 10 from the file data.txt.

The password is stored among several strings, and it is the only human-readable string preceded by several = characters.
## Initial observations

The file data.txt contains binary and human-readable data.
Reading the entire file directly with cat produces a lot of unreadable output.
The strings command can extract human-readable strings from binary files.
The output can then be searched for the relevant pattern using grep.

## Approach

I first used the strings command on data.txt to extract sequences of printable characters.

I then piped the output to grep and searched for lines containing = characters. This reduced the output and made it easier to identify the string containing the password.

## Commands used
### #Connect to Bandit Level 9
ssh bandit9@bandit.labs.overthewire.org -p 2220

### #Extract human-readable strings and search for "="
strings data.txt | grep "=="

## Explanation

strings data.txt: Extracts human-readable character sequences from the binary file.
|: Passes the output of strings to grep.
grep "==": Searches the extracted strings for lines containing ==.
he strings command is useful when a file contains binary data mixed with readable text. Instead of displaying the raw binary contents, it extracts sequences of printable characters.
## Solution

The command:

strings data.txt | grep "=="

displayed the human-readable strings containing the required = pattern.

Among the output, the relevant string was the password for Bandit Level 10.
## Key learnings

strings can extract human-readable text from binary files.
grep can search command output for a particular pattern.
Pipes (|) allow multiple Linux utilities to be combined.
Binary files should not always be treated as ordinary text files.
Filtering command output can make large or noisy results much easier to analyze.
