FROM debian
ENV TS3SERVER_LICENSE=accept
EXPOSE 9987/udp 10011 30033
WORKDIR /opt/teamspeak-server
RUN apt update && apt -y upgrade
RUN [ "apt", "install", "-y", "wget", "bzip2" ]
RUN [ "wget", "https://files.teamspeak-services.com/releases/server/3.13.2/teamspeak3-server_linux_amd64-3.13.2.tar.bz2" ]
RUN [ "tar", "-xf", "teamspeak3-server_linux_amd64-3.13.2.tar.bz2" ]
WORKDIR /opt/teamspeak-server/teamspeak3-server_linux_amd64
RUN chmod +x ts3server
ENTRYPOINT sh ts3server_minimal_runscript.sh