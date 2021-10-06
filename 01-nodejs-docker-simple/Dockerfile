FROM node:lts-buster

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.slashrtc.webapi.version="0.1"

RUN groupadd slashrtc && useradd --no-log-init -r -g slashrtc slashrtc

WORKDIR /home/slashrtc

RUN mkdir app

WORKDIR /home/slashrtc/app

COPY . .

RUN npm install

EXPOSE 3000

CMD node index.js
