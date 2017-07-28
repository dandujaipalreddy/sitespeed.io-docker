FROM sitespeedio/webbrowsers:firefox-54.0-chrome-60.0

MAINTAINER Peter Hedenskog <peter@soulgalore.com>

RUN \
apt-get update && \
apt-get install -y curl && \
curl --silent --location https://deb.nodesource.com/setup_5.x | bash - && \
apt-get install -y \
nodejs \
build-essential --no-install-recommends && \
npm set progress=false && \
npm install -g webcoach && npm cache clean && \
apt-get purge -y curl git build-essential && \
apt-get clean autoclean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD ./scripts/ /home/ppoker/scripts

VOLUME /coach

WORKDIR /coach
