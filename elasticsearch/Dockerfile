# Java on Ubuntu
FROM FROM openjdk:7

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

RUN chown elasticsearch:elasticsearch /opt/elasticsearch-2.4.1 -R

COPY elasticsearch.yml /etc/elasticsearch/config/

USER elasticsearch

CMD ./elasticsearch -Des.network.host=0.0.0.0

EXPOSE 9200
EXPOSE 9300
