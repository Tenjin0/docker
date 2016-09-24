FROM ubuntu:16.04
MAINTAINER Patrice PETIT <patricepetit@hotmail.com>
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g -y bower nodemon
VOLUME ['/var/www:/app']
ADD server.js /app/
ADD package.json /app/
EXPOSE 8080
WORKDIR /app
RUN npm install
CMD node server.js
