---
title: Permissions and Ownership in Linux
published: true
description: Linux
tags: 
---
In Linux, files and directories have three types of permissions (read, write, execute) for three types of users (owner, group, others).
`r` (read): Allows reading the file's contents.
`w` (write): Permits modifying the file's contents.
`x` (execute): Enables executing the file as a program.

## Changing File Permissions with chmod
You can use the chmod command to modify access permissions for files and directories.
- Symbolic Mode:
  ```bash
  $ chmod u+x file.txt  # Add execute permission to the owner
  $ chmod g-w file.txt  # Remove write permission from the group
  $ chmod o=r file.txt  # Set read-only permission for others
  ```

- Octal Mode:
  ```bash
  $ chmod 755 file.txt  # rwxr-xr-x: Owner has all permissions, group has read and execute, others have read and execute
  ```

## Changing File Owner and Group with chown
The chown command lets you change the owner and group of files and directories.
```bash
$ chown newowner file.txt          # Change the file's owner
$ chown newowner:newgroup file.txt # Change both the owner and group of the file
```

## Changing Group Ownership with chgrp
Using the chgrp command, you can change the group ownership of files and directories.
```bash
$ chgrp newgroup file.txt
```

## Viewing File Permissions with ls -l
The ls -l command displays file and directory access permissions, owner, and group.
```bash
$ ls -l
-rwxr-xr-x 1 owner group 1234 Jan 1 12:00 file.txt
```
Understanding and managing permissions and ownership is crucial for maintaining security and proper access control in a Linux system.