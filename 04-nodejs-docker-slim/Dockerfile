FROM node:lts-slim

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.slashrtc.webapi.version="0.4"

RUN groupadd slashrtc && useradd --no-log-init -r -g slashrtc slashrtc

WORKDIR /home/slashrtc

RUN mkdir app

WORKDIR /home/slashrtc/app

COPY package*.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD node index.js
