FROM ubuntu:latest
MAINTAINER mohammad Dadkhah <m.datkhah@gmail.com>

ENV DEBIAN-FRONTEND=noninteractive

RUN apt update && \
    apt upgrade -y vim && \
    apt  install  openssh-server -y && \
    apt install  debconf && \
    apt install  apt-utils && \
    mkdir -p /var/run/sshd && \
    rm -rf /var/lib/apt/lists/* && \
    echo 'root:123!@#abc' | chpasswd 


COPY sshd-hardening.conf /etc/ssh/sshd_config.d/00-enable-root-password.conf






EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]



