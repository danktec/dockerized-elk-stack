# dockerized-elk-stack
3x docker containers running ElasticSearch, Logstash, Kibana with docker-compose

# Dockerfiles
/elasticsearch/Dockerfile
/logstash/Dockerfile
/kibana/Dockerfile

# Config Files
/elasticsearch/conf
/logstash/conf
/kibana/conf

# How It Works
Compile with:

```docker build -t <container_name> /<service>/Dockerfile```

Run with:

```docker-compose up```
