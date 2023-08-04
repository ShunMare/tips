---
title: To set up Logstash and Elasticsearch in separate containers and send log data between them 
published: false
description: description
tags: Logstash, Elasticsearch
---
# To set up Logstash and Elasticsearch in separate containers and send log data between them

## Create a Docker network named "elastic" to connect both containers:
```bash
docker network create elastic
```
## Connect the prepared Logstash container to the "elastic" network:
```bash
docker network connect elastic logstash
```
## Create and run the Elasticsearch Docker container, connecting it to the "elastic" network:
```bash
docker run --network=elastic -p 9200:9200 -p 9300:9300 --name=elasticsearch -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.15.2
```
## After running Elasticsearch, stop it once with Ctrl+C.
## Reconnect Elasticsearch to the "elastic" network:
```bash
docker network connect elastic elasticsearch
```
## Start the Elasticsearch container:
```bash
docker start elasticsearch
```
## Find the IP address of the Elasticsearch container (Note: In Windows, use double quotes for the command):
```bash
docker inspect -f "{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}" elasticsearch
```
## The command docker network inspect elastic is used to retrieve information about the Docker network named "elastic". This command displays detailed information about the network, including its name, ID, creation timestamp, and configuration.
```bash
docker network inspect elastic
```
 Output:
```jason
"Containers": {
  "<CONTAINER_ID>": {
    "Name": "elasticsearch",
    "EndpointID": "<EndpointID>",
    "MacAddress": "00:00:ac:00:00:00",
    "IPv4Address": "172.19.0.3/16",
    "IPv6Address": ""
  },
  "<CONTAINER_ID>": {
    "Name": "logstash",
    "EndpointID": "<EndpointID>",
    "MacAddress": "00:00:ac:00:00:00",
    "IPv4Address": "172.19.0.2/16",
    "IPv6Address": ""
  }
},
```
## Start Logstash container:
```bash
docker start logstash
```
## Access the Logstash container:
```bash
docker exec -it logstash /bin/bash
```
## Update the Logstash pipeline configuration:
```bash
vi /usr/share/logstash/pipeline/logstash.conf
```
## Enter the following configuration in the editor:
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
  elasticsearch {
    hosts => ["http://172.19.0.3:9200"]
    index => "test_index"
  }
  stdout { codec => rubydebug }
}
```
## Save and exit the editor.
Execute Logstash with the updated pipeline configuration:
```bash
/usr/share/logstash/bin/logstash -f /usr/share/logstash/pipeline/logstash.conf
```
## The Logstash process will start, and it will read the data from the specified input file and send it to Elasticsearch, as well as display the output using stdout with the rubydebug codec.
 You should see the following output:
```jason
{
        "host" => "000000000000",
  "@timestamp" => "2023-00-00T00:00:00.000Z",
        "test2" => "test2",
        "test3" => "test3",
        "test" => "test1",
    "@version" => "1",
        "path" => "/usr/share/logstash/logs/test.log"
}
```
## Now, let's access the Elasticsearch container:
Access the Elasticsearch container:
```bash
docker exec -it elasticsearch /bin/bash
```
## To check the count of documents in the "test_index" index:
```bash
curl 172.19.0.3:9200/test_index/_count
```
Output:
```json
{"count":1,"_shards":{"total":1,"successful":1,"skipped":0,"failed":0}}
```
## To retrieve and pretty-print the log data from the "test_index" index:
```bash
curl 172.19.0.3:9200/test_index/_search?pretty
```
 Output:
```json
{
  "_index" : "test_index",
  "_type" : "_doc",
  "_id" : "AAAAAAAAAAaaaaaaaaaa",
  "_score" : 1.0,
  "_source" : {
    "host" : "000000000000",
    "@timestamp" : "2023-00-00T00:00:00.000Z",
    "test2" : "test2",
    "test3" : "test3",
    "test" : "test1",
    "@version" : "1",
    "path" : "/usr/share/logstash/logs/test.log"
  }
}
```
