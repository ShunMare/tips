---
title: File and Directory Operations in Windows Commands
published: true
description: Basic Windows command examples for file and directory operations
tags: Windows
---
## Creating and Removing
- `echo.`: Create an empty file.
  ```bash
  C:\> echo. > newfile.txt
  ```
  mkdir: Create a new directory.
  ```bash
  C:\> mkdir new_directory
  ```

- `del`: Remove files.
  ```bash
  C:\> del file_to_remove.txt
  ```

- `rmdir`: Remove a directory (either empty or with contents).
  ```bash
  C:\> rmdir /s /q directory_to_remove
  ```

## Copying, Moving, and Renaming
- `copy`: Copy files.
  ```bash
  C:\> copy source.txt destination.txt
  ```

- `xcopy`: Copy directories.
  ```bash
  C:\> xcopy /s /i source_directory destination_directory
  ```

- `move`: Move or rename files or directories.
  ```bash
  C:\> move oldname.txt newname.txt
  ```

## Listing and Navigating
- `dir`: List directory contents.
  ```bash
  C:\> dir
  ```

- cd: Display or change the current directory.
  ```bash
  C:\> cd \path\to\directory
  ```

## File Content Viewing
- `type`: Display the entire content of a file.
  ```bash
  C:\> type file.txt
  ```

- `more`: View file content with pagination.
  ```bash
  C:\> more file.txt
  (Note: Windows doesn't have direct equivalents to `head` and `tail` commands in its basic command prompt.)
  ```

## File and Directory Information
- `dir`: Display detailed information about a file or directory.
  ```bash
  C:\> dir file.txt
  (Note: Windows doesn't have a direct equivalent to the `file` command in its basic command prompt.)
  ```

## Searching for Files
- `dir`: Search for files in a directory.
  ```bash
  C:\> dir /s /b \path\to\search\*pattern*.txt
  ```