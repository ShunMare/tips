---
title: To pull the Ubuntu image and run Logstash in an Ubuntu environment 
published: false
description: description
tags: Ubuntu, Logstash
---
# To pull the Ubuntu image and run Logstash in an Ubuntu environment

## Docker Ubuntu
Pull the latest Ubuntu image from Docker Hub using the following command:
```bash
docker pull ubuntu:latest
```
Explanation:
- `docker pull` is used to download a Docker image from a registry (in this case, the Docker Hub).
- `ubuntu:latest` specifies the image name and tag. In this case, we are pulling the latest version of the Ubuntu image.
After pulling the image, you will see a summary of image vulnerabilities and recommendations from Docker Scout. You can view this information using the command:
  ```bash
  docker scout quickview ubuntu:latest
  ```
## Run Ubuntu Container with Bash Shell
```bash
docker run -it --name=logstash ubuntu:latest /bin/bash
```
Explanation:
- `docker run` is used to create and start a new container from an image.
- `-it` enables interactive mode with a pseudo-TTY (terminal) for the container.
- `--name=logstash` assigns the name "logstash" to the container.
- `ubuntu:latest` specifies the image to use for the container.
- `/bin/bash` is the command to execute inside the container, which starts a Bash shell.
After running the command, you will be inside the Ubuntu container with the root user (`root@<container_id>:/`). You can interact with the container and execute commands within the Ubuntu environment.
This command updates the package lists from the Ubuntu repositories, so the container can fetch the latest package information before installing any new packages.
## Update the package lists for Ubuntu repositories:
```bash
apt-get update
```
## Install essential packages (wget, sudo, gpg, systemctl, apt-transport-https, and vim):
This command installs the specified packages along with their dependencies. The -y option automatically confirms any prompts during the installation process.
```bash
apt-get install -y wget sudo gpg systemctl apt-transport-https vim
```
## The following commands are executed in the Ubuntu container for setting up Logstash:
1. Update the package lists for Ubuntu repositories:
 Explanation: This command downloads the GPG signing key for Elasticsearch artifacts from the given URL and adds it to the keyring using apt-key add command. The warning about the deprecation of apt-key is displayed, but the key is still added successfully.
    ```bash
    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
    ```
2. Add the Elastic repository to the sources.list:
 Explanation: This command appends the Elastic repository URL to the sources.list.d directory, which contains additional APT package repositories.
    ```bash
    echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-7.x.list
    ```
3. Update the package lists:
 Explanation: This command updates the package lists from all configured repositories, including the newly added Elastic repository.
    ```bash
    sudo apt-get update
    ```
4. Install Logstash:
 Explanation: This command installs Logstash, which is the data processing component of the Elastic Stack.
    ```bash
    sudo apt-get install logstash
    ```
## The following commands are executed in the Ubuntu container to create the Logstash configuration:
1. Change directory to /usr/share/logstash/:
 Explanation: This command changes the current working directory to /usr/share/logstash/, where the Logstash configuration files will be created.
    ```bash
    cd /usr/share/logstash/
    ```
2. Create a logs directory:
 Explanation: This command creates a new directory named logs inside /usr/share/logstash/ to store log files.
    ```bash
    mkdir logs
    ```
3. Create and edit a test log file named test.log:
    ```bash
    sudo vi logs/test.log
    ```
    Contents of test.log:
    ```log
    {"test": "test1", "test2": "test2", "test3": "test3"}
    ```
4. Create a pipeline directory:
    ```bash
    mkdir pipeline
    ```
5. Create and edit the Logstash configuration file named logstash.conf:
    ```bash
    sudo vi pipeline/logstash.conf
    ```
    Contents of logstash.conf:
    ```conf
    input {
      file {
        path => "/usr/share/logstash/logs/test.log"
        start_position => "beginning"
        sincedb_path => "/dev/null"
        codec => "json"
      }
    }

    output {
      stdout { codec => rubydebug }
    }
    ```
## After setting up the Logstash configuration, the following command is executed to run Logstash:
```bash
/usr/share/logstash/bin/logstash -f /usr/share/logstash/pipeline/logstash.conf
```
Output:
```log
{
        "host" => "000000000000",
    "@version" => "1",
        "test2" => "test2",
        "path" => "/usr/share/logstash/logs/test.log",
  "@timestamp" => 2023-00-00T00:00:00.000Z,
        "test" => "test1",
        "test3" => "test3"
}
```
