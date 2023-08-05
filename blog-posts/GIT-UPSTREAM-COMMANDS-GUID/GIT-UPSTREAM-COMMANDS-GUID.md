---
title: Git Upstream Commands Guide 
published: true
description: description
tags: Git
cover_image: 
---
# Git Upstream Commands Guide

Git's upstream refers to a default remote branch for a given branch. Setting an upstream makes it easier to synchronize and compare changes between the branch and its corresponding remote branch.

## Setting Up Upstream

```bash
git remote add upstream <original-repository-url>
```

This command configures the original repository as a new remote called "upstream".

## Configuring an Upstream for a Branch

To set the upstream for a branch:

```bash
git branch --set-upstream-to=<remote>/<branch> <local-branch>
```

For instance, to set the `main` branch of the `origin` remote as the upstream for the local `feature` branch:

```bash
git branch --set-upstream-to=origin/main feature
```

## Checking Upstreams

To view all local branches and their respective upstreams:

```bash
git branch -vv
```

## Pushing to Upstream

To push changes from the current branch to its upstream:

```bash
git push
```

## Pulling from Upstream

To pull changes from the upstream to the current branch:

```bash
git pull
```

By setting up upstreams, you no longer need to specify the remote name and branch name each time you run `git push` or `git pull`. This enhances the efficiency of your workflow.
