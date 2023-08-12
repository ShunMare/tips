---
title: Standard Windows Commands and Their Outputs
published: true
description: Basic Windows Command Prompt commands and their outputs
tags: Windows
---

## File Operations
- `dir`: List directory contents
  ```bash
  C:\> dir
  2023-08-11  10:00 AM    <DIR>          dir1
  2023-08-11  09:58 AM                20 file1.txt
  2023-08-11  09:59 AM                30 file2.txt
  ```

- `cd`: Print working directory
  ```bash
  C:\> cd
  C:\Users\user
  ```

## Text Operations
- `type`: Display file content
  ```bash
  C:\> type file1.txt
  This is the content of file1.
  ```

- `more`: Display the beginning of a file (Windows doesn't have an exact equivalent to head, but more can be used to view the contents)
  ```bash
  C:\> more file1.txt
  First line of the file.
  ```

- `more`: Display the end of a file (Again, Windows doesn't have an exact tail equivalent, but you can scroll through with more)
  ```bash
  C:\> more file1.txt
  Last line of the file.
  ```

## System Information
- `systeminfo`: Display system information (This provides a lot of information, more than uname -a in Linux)
  ```bash
  C:\> systeminfo
  ```

- `wmic OS get FreePhysicalMemory,TotalVisibleMemorySize /Value`: Display memory usage (This is a bit more complex in Windows compared to Linux's `free`)
  ```bash
  C:\> wmic OS get FreePhysicalMemory,TotalVisibleMemorySize /Value
  ```

## Networking
- `ping`: Test network connection
  ```bash
  C:\> ping google.com
  ```

## Miscellaneous
- `echo`: Display a line of text
  ```bash
  C:\> echo Hello, World!
  Hello, World!
  ```

- `doskey /history`: Display command history (This might not capture all history like Linux's history command, but it's the closest built-in command)
  ```bash
  C:\> doskey /history
  ```