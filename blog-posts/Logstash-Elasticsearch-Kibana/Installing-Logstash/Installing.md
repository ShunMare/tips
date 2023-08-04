---
title: Installing Logstash 
published: true
description: description
tags: Logstash
---
## Installing from a Downloaded Binary

1. Download the Logstash installation file for your host environment—​TAR.GZ, DEB, ZIP, or RPM from [here](https://www.elastic.co/downloads).
2. Unpack the file. Do not install Logstash into a directory path that contains colon (:) characters.

Note: These packages are free to use under the Elastic license. They contain open source and free commercial features and access to paid commercial features. 

## Installing from Package Repositories

For APT and YUM based distributions, you can use a package manager to install Logstash.

### APT

1. Download and install the Public Signing Key:
    ```bash
    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elastic-keyring.gpg
    ```

2. Install the apt-transport-https package:
    ```bash
    sudo apt-get install apt-transport-https
    ```

3. Save the repository definition:
    ```bash
    echo "deb [signed-by=/usr/share/keyrings/elastic-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-8.x.list
    ```

4. Update and install:
    ```bash
    sudo apt-get update && sudo apt-get install logstash
    ```

### YUM

1. Download and install the public signing key:
    ```bash
    sudo rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
    ```

2. Add the following in your /etc/yum.repos.d/ directory in a file with a .repo suffix, for example logstash.repo:<br>
[logstash-8.x]<br>
name=Elastic repository for 8.x packages<br>
baseurl=https://artifacts.elastic.co/packages/8.x/yum<br>
gpgcheck=1<br>
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch<br>
enabled=1<br>
autorefresh=1<br>
type=rpm-md<br>

3. Install:
    ```bash
    sudo yum install logstash
    ```

## Docker

Images are available for running Logstash as a Docker container. They are available from the Elastic Docker registry. See [Running Logstash on Docker](https://www.elastic.co/guide/en/logstash/current/running-logstash-on-docker.html) for details on how to configure and run Logstash Docker containers.
