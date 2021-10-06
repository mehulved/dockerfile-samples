FROM node:lts-alpine

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.slashrtc.webapi.version="0.5"

RUN addgroup -S slashrtc && adduser -S slashrtc -G slashrtc

WORKDIR /home/slashrtc

RUN mkdir app

WORKDIR /home/slashrtc/app

COPY package*.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD node index.js
