---
title: Git Commands Mastering Basics, Merge, and Rebase 
published: true
description: description
tags: Git
---
## Group Changes

### Lists all local branches in the current repository
```bash
git branch
```

### Creates a new branch
```bash
git branch [branch-name]
```

### Switches to the specified branch and updates the working directory
```bash
git checkout [branch-name]
```

### Combines the specified branch’s history into the current branch. 
This command is used when you want to combine changes from two different branches. It creates a new "merge commit" in the branch that preserves the history of both branches.
```bash
git merge [branch]
```

### Deletes the specified branch
```bash
git branch -d [branch-name]
```

### Rebase
The `git rebase` command moves or combines a sequence of commits to a new base commit. Essentially, it's a way to integrate changes from one branch into another, but it differs from `merge` by rewriting commit history. Use it carefully, as it can complicate the commit history and is not recommended if you're working on a public branch that others are using.
```bash
git rebase [base]
```
