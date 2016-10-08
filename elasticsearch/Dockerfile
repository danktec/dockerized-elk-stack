FROM ubuntu

USER root

WORKDIR /root

RUN apt-get update -y && \
    apt-get install openjdk-8-jre -y && \
    curl -L -O https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.1/elasticsearch-2.4.1.tar.gz && \
    tar -xvf elasticsearch-2.4.1.tar.gz

WORKDIR /root/elasticsearch-2.4.1/bin

#COPY default.conf /etc/nginx/conf.d/

CMD ./elasticsearch

EXPOSE 9200
