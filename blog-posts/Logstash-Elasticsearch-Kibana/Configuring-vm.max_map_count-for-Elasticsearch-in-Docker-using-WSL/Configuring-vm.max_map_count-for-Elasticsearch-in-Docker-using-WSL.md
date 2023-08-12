---
title: Configuring vm.max_map_count for Elasticsearch in Docker using WSL
published: false
description: Configure vm.max_map_count for Elasticsearch in Docker using WSL.
tags: Docker, Elasticsearch, WSL
---

## Configuring vm.max_map_count for Elasticsearch in Docker using WSL

When running Elasticsearch on Docker, you might encounter an error message like the following if the default value of vm.max_map_count is too low:

```bash
max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
```
To resolve this error, you need to use Windows Subsystem for Linux (WSL) to properly configure the value of vm.max_map_count.

Accessing Docker Desktop's WSL Environment
Open a command prompt and access the WSL environment of Docker Desktop using the following command:

```bash
PS C:\work\project\logstash> wsl -d docker-desktop
```
Modifying System Settings
Once inside the WSL environment, use the following command to change the value of vm.max_map_count:

```bash
DESKTOP-XXXXXXX:/path/to/directory# sysctl -w vm.max_map_count=262144
```
Exiting the WSL Environment
Exit the WSL environment using the following command:

```bash
DESKTOP-XXXXXXX:/path/to/directory# exit
```
Following these steps should resolve the Elasticsearch error related to vm.max_map_count, allowing Elasticsearch to run smoothly.