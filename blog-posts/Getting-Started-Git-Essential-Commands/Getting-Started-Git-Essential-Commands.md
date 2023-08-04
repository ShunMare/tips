---
title: Getting Started with Git Essential Commands 
published: false
description: description
tags: Git
---
# Getting Started with Git: Essential Commands

# Git Commands 

## Configure Tooling

Sets the name you want attached to your commit transactions
```bash
git config --global user.name "[name]" 
```

Sets the email you want attached to your commit transactions
```bash
git config --global user.email "[email address]" 
```

## Create Repositories

Creates a new local repository with the specified name
```bash
git init [project-name]
```

Downloads a project and its entire version history
```bash
git clone [url]
```

## Make Changes

Lists all new or modified files to be committed
```bash
git status
```

Shows file differences not yet staged
```bash
git diff
```

Snapshots the file in preparation for versioning
```bash
git add [file]
```

Records file snapshots permanently in version history
```bash
git commit -m "[descriptive message]"
```

## Group Changes

Lists all local branches in the current repository
```bash
git branch
```

Creates a new branch
```bash
git branch [branch-name]
```

Switches to the specified branch and updates the working directory
```bash
git checkout [branch-name]
```

Combines the specified branch’s history into the current branch
```bash
git merge [branch]
```

Deletes the specified branch
```bash
git branch -d [branch-name]
```

## Refactor Filenames

Deletes the file from the working directory and stages the deletion
```bash
git rm [file]
```

Changes the file name and prepares it for commit
```bash
git mv [file-original] [file-renamed]
```

## Suppress Tracking

Lists the files and directories that git should ignore
```bash
.gitignore
```

## Review History

Displays commit history
```bash
git log
```

Shows content differences between two branches
```bash
git diff [first-branch]...[second-branch]
```

## Save Fragments

Temporarily stores all modified tracked files
```bash
git stash
```

Restores the most recently stashed files
```bash
git stash pop
```

Lists all stashed changesets
```bash
git stash list
```

Discards the most recently stashed changeset
```bash
git stash drop
```

## Synchronize Changes

Downloads all history from the repository bookmark
```bash
git fetch [bookmark]
```

Combines bookmark’s branch into current local branch
```bash
git merge [bookmark]/[branch]
```

Uploads all local branch commits to gitHub
```bash
git push [alias] [branch]
```

Downloads bookmark history and incorporates changes
```bash
git pull
```
