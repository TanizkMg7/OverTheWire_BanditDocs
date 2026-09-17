# Bandit Level 00 → Level 00

## Objective

Connect to the Bandit Level 0 server using SSH and retrieve the password required to access Level 1.

## Initial observations

The challenge provides a hostname, port number, username, and password.
SSH (Secure Shell) is used to establish a remote terminal session.
The given username is bandit0.
The default SSH port is 22, but Bandit uses a non-standard port.

## Approach

I used SSH to connect to the OverTheWire Bandit server with the provided username and port. After entering the password, I successfully accessed the Level 0 shell.

## Commands used
ssh bandit0@bandit.labs.overthewire.org -p 2220

## Explanation

ssh: A command used to establish a secure remote connection.
bandit0: The username provided for Level 0.
bandit.labs.overthewire.org: The hostname of the Bandit server.
-p 2220: Specifies the port on which the SSH server is listening.

## Solution

The SSH connection was established successfully, and I gained access to the Bandit Level 0 terminal.

## Key learnings

SSH is used for secure remote terminal access.
The -p option specifies a custom SSH port.
A remote server can be accessed using a username, hostname, and password.
Linux terminal commands can be executed on a remote machine through SSH.

## References

OverTheWire Bandit
SSH manual page
