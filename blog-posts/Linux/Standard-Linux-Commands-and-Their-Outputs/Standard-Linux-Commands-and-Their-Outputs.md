---
title: Standard Linux Commands and Their Outputs
published: true
description: 
tags: Linux
---
## File Operations
- `ls`: List directory contents
  ```bash
  $ ls
  file1.txt  file2.txt  dir1/
  ```

- `pwd`: Print working directory
  ```bash
  $ pwd
  /home/user
  ```

## Text Operations
- `cat`: Display file content
  ```bash
  $ cat file1.txt
  This is the content of file1.
  ```

- `head`: Display the beginning of a file
  ```bash
  $ head file1.txt
  First line of the file.
  ```

- `tail`: Display the end of a file
  ```bash
  $ tail file1.txt
  Last line of the file.
  ```

## System Information
- `uname -a`: Display system information
  ```bash
  $ uname -a
  Linux hostname 5.4.0-42-generic #46-Ubuntu SMP Fri Jul 10 00:24:02 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
  ```

- `free`: Display memory usage
  ```bash
  $ free -h
            total        used        free      shared  buff/cache   available
  Mem:      7.7Gi       1.2Gi       5.8Gi       123Mi       717Mi       6.2Gi
  Swap:     2.0Gi          0B       2.0Gi
  ```

## Networking
- `ping`: Test network connection
  ```bash
  $ ping -c 4 google.com
  PING google.com (172.217.22.14) 56(84) bytes of data.
  64 bytes from fra15s11-in-f14.1e100.net (172.217.22.14): icmp_seq=1 ttl=53 time=29.3 ms
  ...
  ````

## Miscellaneous
- `echo`: Display a line of text
  ```bash
  $ echo "Hello, World!"
  Hello, World!
  ```

- `history`: Display command history
  ```bash
  $ history
  1  ls
  2  cd ..
  3  pwd
  ...
  ```