---
title: Disk Usage Commands in Linux
published: true
description: 
tags: Linux
---

## `df`: Display Filesystem Disk Space Usage
The `df` command is used to display the disk space usage of mounted filesystems.

- Basic Usage:
  ```bash
  $ df
  ```

- Common Options:
  - `-h` or `--human-readable`: Display sizes in a human-readable format (K, M, G).
    ```bash
    $ df -h
    ```
  - `-T` or `--print-type`: Display filesystem types.
    ```bash
    $ df -T
    ```
  - `-a` or `--all`: Display all filesystems, including pseudo, duplicate, inaccessible filesystems.
    ```bash
    $ df -a
    ```
  - `-i` or `--inodes`: Display inode information.
    ```bash
    $ df -i
    ```

## `du`: Estimate File and Directory Space Usage
  The du command estimates disk space usage of files and directories.

- Basic Usage:
  ```bash
  $ du /path/to/directory
  ```

- Common Options:
  - `-h` or `--human-readable`: Display sizes in a human-readable format (K, M, G).
    ```bash
    $ du -h /path/to/directory
    ```

- `-s` or `--summarize`: Display only the total size of the specified directory.
  ```bash
  $ du -s /path/to/directory
  ```

- `-a` or `--all`: Display both directory and file information.
  ```**bash**
  $ du -a /path/to/directory
  ```

- `-c` or `--total`: Display the grand total.
  ```bash
  $ du -c /path/to/directory
  ```

- `--max-dept`h=N: Display information up to a depth of N directories.
  ```bash
  $ du --max-depth=1 /path/to/directory
  ```

Understanding the `df` and `du` commands is essential for monitoring disk space usage and managing file storage effectively.