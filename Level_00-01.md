# Bandit Level 00 → Level 01

## Objective

The objective is to log in to the Bandit Level 0 server using SSH and retrieve the password for the next level, Level 1.

## Initial observations

The server hostname is bandit.labs.overthewire.org.
The SSH port is 2220.
The username is bandit0.
After logging in, the password for the next level is stored in a file named readme in the home directory.

## Approach

I connected to the Bandit server using SSH with the provided credentials. After logging in, I used the ls command to list the files in the home directory. I found a file named readme, which appeared to contain the password for the next level.

I then used the cat command to display the contents of the file.

## Commands used

### Connect to the Bandit Level 0 server 
ssh bandit0@bandit.labs.overthewire.org -p 2220 
### List files in the current directory 
ls 
### Display the contents of the readme file 
cat readme

## Explanation

ssh bandit0@bandit.labs.overthewire.org -p 2220: Establishes an SSH connection to the Bandit server using the Level 0 username and custom port.
ls: Lists files and directories in the current working directory.
cat readme: Reads and displays the contents of the readme file in the terminal.

## Solution

The password for Level 1 was successfully retrieved by reading the readme file using the cat command.

The password should be copied and used when connecting to the next level.

## Key learnings

SSH can be used to connect to remote Linux systems.
ls is used to inspect the contents of a directory.
cat displays the contents of a file.
The home directory is the default working directory after logging in.
File contents can contain credentials or other information needed to progress through a challenge.
