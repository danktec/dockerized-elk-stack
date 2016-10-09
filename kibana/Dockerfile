FROM node:6.7.0

# Environment setup
USER root
WORKDIR /opt

RUN groupadd -r kibana && useradd -r -g kibana kibana

RUN apt-get update -y && \
    apt-get install telnet curl -y && \
    curl -O https://download.elastic.co/kibana/kibana/kibana-4.6.1-linux-x86_64.tar.gz && \
    tar -xvf kibana-4.6.1-linux-x86_64.tar.gz && \
    mv kibana-4.6.1-linux-x86_64 kibana

RUN chown kibana:kibana /opt/kibana -R

COPY config/kibana.yml /opt/kibana/config/kibana.yml

USER kibana
WORKDIR /opt/kibana
CMD bin/kibana

# Expose ourselves
EXPOSE 5601
