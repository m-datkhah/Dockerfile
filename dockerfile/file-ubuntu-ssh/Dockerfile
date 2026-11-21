FROM ubuntu:latest
MAINTAINER mohammad Dadkhah <m.datkhah@gmail.com>

ENV DEBIAN-FRONTEND=noninteractive

RUN apt update && apt upgrade -y vim &&  apt  install  openssh-server -y 
RUN apt install  debconf 
RUN apt install  apt-utils
RUN mkdir -p /var/run/sshd 
RUN echo 'root:123!@#abc' | chpasswd 


COPY sshd-hardening.conf /etc/ssh/sshd_config.d/00-enable-root-password.conf




RUN rm -rf /var/lib/apt/lists/*


EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]



