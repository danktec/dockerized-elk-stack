# Java on Ubuntu
FROM openjdk:8

# Environment setup
USER root
WORKDIR /opt
ENV ES_HOME /etc/elasticsearch
RUN groupadd -r elasticsearch && useradd -r -g elasticsearch elasticsearch

# Get what we need
RUN apt-get update -y && \
    apt-get install curl telnet -y && \
    curl -L -O https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.1/elasticsearch-2.4.1.tar.gz && \
    tar -xvf elasticsearch-2.4.1.tar.gz

WORKDIR /opt/elasticsearch-2.4.1/bin

VOLUME /data

RUN chown elasticsearch:elasticsearch /opt/elasticsearch-2.4.1 -R

COPY config/elasticsearch.yml /opt/elasticsearch-2.4.1/config/elasticsearch.yml

USER elasticsearch
CMD ./elasticsearch

# Expose ourselves
EXPOSE 9200
EXPOSE 9300
