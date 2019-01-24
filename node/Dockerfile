FROM node:8.15.0-stretch

MAINTAINER Luca Calcaterra

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install build-essential -y && \
	apt-get install python -y 


RUN groupadd -g 999 openhabcloud && \
	useradd -r -u 999 -g openhabcloud openhabcloud

# Add proper timezone
RUN apt-get install tzdata && \
	cp /usr/share/zoneinfo/Europe/Berlin /etc/localtime && \
	echo "Europe/Rome" >  /etc/timezone

RUN mkdir -p /opt/openhabcloud
COPY ./package.json ./config.json /opt/openhabcloud/
RUN mkdir /data
RUN ln -s /opt/openhabcloud/package.json /data
WORKDIR /data
RUN npm install
# && npm rebuild bcrypt --build-from-source

ENV NODE_PATH /data/node_modules

WORKDIR /opt/openhabcloud
RUN  chown -R openhabcloud:openhabcloud /opt/openhabcloud && \
        chmod -R 777 /opt/openhabcloud

USER openhabcloud

ADD . /opt/openhabcloud

EXPOSE 3000
CMD ["node", "app.js"]
