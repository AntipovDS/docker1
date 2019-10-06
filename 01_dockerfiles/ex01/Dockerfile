FROM debian
LABEL maintainer="taethan@student.21-school.ru"
ENV TS3SERVER_LICENSE=accept
WORKDIR /home/teamspeak

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y wget bzip2 && \
    wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.9.1.tar.bz2

WORKDIR /home/teamspeak/teamspeak3-server_linux_amd64
EXPOSE 9987/udp 10011 30033
ENTRYPOINT sh ts3server_minimal_runscript.sh

# docker build -t ex01 .
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01

# https://hub.docker.com/_/teamspeak
# https://github.com/docker-library/docs/tree/master/teamspeak/
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-ubuntu-16-04-64-bit
