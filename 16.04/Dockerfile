FROM       ubuntu:16.04
MAINTAINER Phakin Cheangkrachange "https://github.com/teamsoo"

RUN sed -i 's/http:\/\//http:\/\/th./g' /etc/apt/sources.list
RUN sed -i 's/http:\/\/th.security/http:\/\/security/g' /etc/apt/sources.list

RUN mkdir /root/data

RUN apt-get update

RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd

RUN echo 'root:teamsoo' |chpasswd

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-D"]
