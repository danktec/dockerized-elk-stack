# Java on Ubuntu
FROM openjdk:8

# Environment setup
USER root
WORKDIR /opt
ENV LS_HOME /etc/logstash
RUN groupadd -r logstash && useradd -r -g logstash logstash

# Get what we need to make this fiasco work
RUN apt-get update -y && \
    apt-get install apt-transport-https telnet -y && \
    wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | apt-key add - && \
    echo "deb https://packages.elastic.co/logstash/2.4/debian stable main" | tee -a /etc/apt/sources.list && \
    apt-get update -y && apt-get install logstash -y

WORKDIR /opt/logstash

RUN chown logstash:logstash /opt/logstash -R

#COPY config/elasticsearch.yml /opt/elasticsearch-2.4.1/config/elasticsearch.yml

USER elasticsearch
CMD ./elasticsearch

# Expose ourselves
EXPOSE 6999
