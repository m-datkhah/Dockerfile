FROM ubuntu:latest

MAINTAINER mohammad Dadkhah <m.datkhah@gmail.com>


RUN apt update && \
apt upgrade -y && \
apt install -y  openjdk-8-jre-headless \
curl \
vim \
tar \
coreutils \
adduser && \
rm -rf /var/lib/apt/list/*

RUN  groupadd -r nexus && \ 
     useradd -r -g nexus -d /opt/nexus  nexus 
RUN mkdir /opt/nexus /opt/sonatype-work
RUN chown -R nexus:nexus  /opt/nexus /opt/sonatype-work


COPY nexus*.tar.gz /tmp/

RUN tar -xzf /tmp/nexus*.tar.gz -C /opt/nexus --strip-components=1 && \
    rm -f /tmp/nexus*.tar.gz && \
    chown -R nexus:nexus /opt/nexus


ENV SONATYPE_WORK=/opt/sonatype-work
USER nexus

WORKDIR /opt/nexus

EXPOSE 8081

CMD ["/opt/nexus/bin/nexus", "run"]
