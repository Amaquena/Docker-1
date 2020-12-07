FROM debian
ENV TS3SERVER_LICENSE=accept
EXPOSE 9987/udp 10011 30033
WORKDIR /opt/teamspeak-server
# RUN [ "apt", "update" ]
RUN apt update && apt -y upgrade
# RUN adduser --disabled-login teamspeak
# RUN su teamspeak
RUN [ "apt", "install", "-y", "wget", "bzip2" ]
RUN [ "wget", "https://files.teamspeak-services.com/releases/server/3.13.2/teamspeak3-server_linux_amd64-3.13.2.tar.bz2" ]
RUN [ "tar", "-xf", "teamspeak3-server_linux_amd64-3.13.2.tar.bz2" ]
# RUN mv teamspeak3-server_linux_amd64/* /opt/teamspeak-server
# RUN mv /teamspeak3-server_linux_x86/* /opt/teamspeak-server
WORKDIR /opt/teamspeak-server/teamspeak3-server_linux_amd64
RUN chmod +x ts3server
# RUN touch .ts3server_license_accepted
ENTRYPOINT ./ts3server_startscript.sh start
# ENTRYPOINT [ "sh", "ts3server_startscript.sh" ]