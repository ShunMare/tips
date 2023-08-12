---
title: Text Processing in Linux
published: true
description: 
tags: Linux
---

## Searching within Text
- `grep`: Search for a pattern within files.
  - `-i`: Ignore case.
  - `-r` or `-R`: Recursively search in directories.
  - `-v`: Invert the search (return lines that don't match).
    ```bash
    $ grep "search_term" file.txt
    This line contains the search_term.
    ```
    ```bash
    $ grep -i "Search_Term" file.txt
    This line contains the search_term.
    ```

## Filtering and Transforming Text
- `awk`: A versatile programming language for working on files.
  ```bash
  $ echo -e "a 1\nb 2\nc 3" | awk '{print $2}'
  1
  2
  3
  ```

- `sed`: Stream editor for filtering and transforming text.
  ```bash
  $ echo "Hello World" | sed 's/World/Universe/'
  Hello Universe
  ```

## Sorting and Counting
- `sort`: Sort lines in text files.
  - `-r`: Reverse the result of comparisons (descending).
  - `-n`: Compare according to string numerical value.
    ```bash
    $ echo -e "banana\napple\ncherry" | sort
    apple
    banana
    cherry
    ```

- `uniq`: Report or omit repeated lines.
  - `-c`: Prefix lines by the number of occurrences.
    ```bash
    $ echo -e "a\na\nb\nb\nb\nc" | uniq -c
      2 a
      3 b
      1 c
    ```

  `wc`: Count words, lines, and characters in files.
    - `-l`: Count lines.
    - `-w`: Count words.
    - `-c`: Count bytes.
      ```bash
      $ echo "Hello World" | wc -w
      2
      ```

## Text Display
- `cat`: Concatenate and display the content of files.
  ```bash
  $ cat file.txt
  This is the content of file.txt.
  ```

- `tac`: Display files in reverse.
  ```bash
  $ echo -e "line1\nline2\nline3" | tac
  line3
  line2
  line1
  ```

- `nl`: Number lines of files.
  ```bash
  $ echo -e "line1\nline2\nline3" | nl
  1  line1
  2  line2
  3  line3
  ```

  - `head`: Display the beginning of a file.
    - `-n`: Specify the number of lines to show.
      ```bash
      $ echo -e "line1\nline2\nline3" | head -n 2
      line1
      line2
      ```

  - `tail`: Display the end of a file.
    - `-n`: Specify the number of lines to show.
    - `-f`: Follow the content of a file in real-time.
      ```bash
      $ echo -e "line1\nline2\nline3" | tail -n 2
      line2
      line3
      ```