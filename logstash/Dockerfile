# Java on Ubuntu
FROM openjdk:8

# Environment setup
USER root
WORKDIR /opt
ENV LS_HOME /etc/logstash
RUN groupadd -r logstash && useradd -r -g logstash logstash

# Get what we need to make this fiasco work
RUN apt-get update -y && \
    apt-get install apt-transport-https telnet curl -y && \
    wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | apt-key add - && \
    echo "deb https://packages.elastic.co/logstash/2.4/debian stable main" | tee -a /etc/apt/sources.list && \
    apt-get update -y && apt-get install logstash -y

WORKDIR /opt/logstash

RUN chown logstash:logstash /opt/logstash -R

COPY config/*.conf /etc/logstash/conf.d/

USER logstash
CMD bin/logstash agent -f /etc/logstash/conf.d/
#CMD sleep 10 && curl elasticsearch:9200
#CMD bash

# Expose ourselves
EXPOSE 5044
