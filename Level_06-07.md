# Bandit Level 06 → Level 07

## Objective

The objective is to retrieve the password for Bandit Level 7 from a file somewhere on the server that satisfies the following conditions:

Owned by user bandit7
Owned by group bandit6
Exactly 33 bytes in size

## Initial observations

Unlike the previous level, the required file is not necessarily inside the current directory.
The search needs to be performed throughout the server.
The find command can search from the root directory (/) and filter files based on ownership, group, and size.
Some directories may produce Permission denied messages during the search.
## Approach

I used the find command starting from / to search the entire filesystem.

I filtered the results using:

-type f to search only for regular files.
-user bandit7 to find files owned by bandit7.
-group bandit6 to find files belonging to the bandit6 group.
-size 33c to find files exactly 33 bytes in size.

I also redirected error messages to /dev/null so that permission-related errors would not clutter the output.

After finding the matching file, I used cat to read its contents.

## Commands used

### #Connect to Bandit Level 6 
ssh bandit6@bandit.labs.overthewire.org -p 2220
### #Search the entire server for the required file 
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null 
### #Read the identified file 
cat /var/lib/dpkg/info/bandit7.password

## Explanation

find /: Starts the search from the root directory, allowing the entire filesystem to be searched.

-type f: Restricts the search to regular files.

-user bandit7: Searches for files owned by the user bandit7.

-group bandit6: Searches for files belonging to the group bandit6.

-size 33c: Searches for files exactly 33 bytes in size. The c represents bytes.

2>/dev/null: Redirects standard error messages, such as Permission denied, to /dev/null.

cat: Displays the contents of the identified file.

## Solution

The required file was found by searching the entire filesystem using the specified ownership, group, and size conditions.

## Key learnings

find can search the entire filesystem starting from /.

Files can be searched based on their owner using -user.

Files can be searched based on their group using -group.

File size can be used as a search condition with -size.

2>/dev/null can suppress unwanted error messages.

File ownership and permissions are important concepts in Linux security.
