---
title: Disk Usage Commands in Windows
published: true
description: Understanding and using disk usage commands in Windows.
tags: Windows
---

## `chkdsk`: Check Disk for System Errors
The `chkdsk` command is used to check the file system and file system metadata of a volume for logical and physical errors.

- Basic Usage:
  ```bash
  C:\> chkdsk
  ```
- Common Options:
  - `/f`: Fixes errors on the disk.
    ```bash
    C:\> chkdsk /f
    ```
  - `/r`: Locates bad sectors and recovers readable information.
    ```bash
    C:\> chkdsk /r
    ```
  - `/x`: Forces the volume to dismount first, if necessary.
    ```bash
    C:\> chkdsk /x
    ```

## `dir`: Display File and Directory Details
The `dir` command is used to display a list of files and subdirectories in a directory.

- Basic Usage:
  ```bash
  C:\> dir C:\path\to\directory
  ```
- Common Options:
  - `/s`: Displays files in the specified directory and all subdirectories.
    ```bash
    C:\> dir /s C:\path\to\directory
    ```
  - `/w`: Uses wide list format.
    ```bash
    C:\> dir /w C:\path\to\directory
    ```
  - `/a`: Displays all files, including hidden and system files.
    ```bash
    C:\> dir /a C:\path\to\directory
    ```
  - `/q`: Displays the owner of the file.
    ```bash
    C:\> dir /q C:\path\to\directory
    ```
Understanding the `chkdsk` and `dir` commands is essential for monitoring disk space usage and managing file storage effectively in Windows.