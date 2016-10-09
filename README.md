# dockerized-elk-stack
3x docker containers running ElasticSearch, Logstash, Kibana with docker-compose

# Starting the Stack

```docker-compose up```

This starts all containers and links them together, exposing ports and mapping the ES data volume to /data on the host.

# Restarting Containers

After making config file changes you can restart the stack with:

``` docker-compose down```
``` docker-compose build```
``` docker-compose up```

# Manually Running a Container

```docker run -itd -p 9200:9200 -p 9300:9300 -v <local_data_dir>:/data <container_name>```

# Dependencies
 - python
 - pip
 - docker-engine (docker)
 - docker-compose

# Notes

Kibana dashboard data is stored in the .kibana ES index. Therefore the ES container is the only one which requires any data persistence.

