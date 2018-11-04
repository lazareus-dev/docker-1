FROM	debian

RUN		apt-get update \
		&& apt-get install -y bzip2 ca-certificates wget

RUN		useradd ts
WORKDIR /home/ts
	
RUN		wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
		&& tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz \
		&& rm teamspeak3-server_linux-amd64-3.0.11.2.tar.gz

WORKDIR teamspeak3-server_linux-amd64
RUN		touch .ts3server_license_accepted
EXPOSE	9987/udp 
USER	ts
ENTRYPOINT ["/home/ts/teamspeak3-server_linux-amd64/ts3server_minimal_runscript.sh"]

