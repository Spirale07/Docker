FROM debian:jessie

LABEL maintainer="tlaberro@student.42.fr"

RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget bzip2 -y

ENV TS3SERVER_LICENSE accept

EXPOSE 9987/udp 10011 30033

ADD creating_server.sh /teamspeak/
RUN sh /teamspeak/creating_server.sh

CMD sh /teamspeak/ts3server_minimal_runscript.sh

//docker build -t teamspeak .
//docker run --name teamspeak -d -p 9987:9987/udp -p 30033:30033 -p 10011:10011 teamspeak