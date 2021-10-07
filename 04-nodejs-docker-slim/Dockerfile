FROM node:lts-slim

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.tutorial.webapi.version="0.4"

RUN groupadd tutorial && useradd --no-log-init -r -g tutorial tutorial

WORKDIR /home/tutorial

RUN mkdir app

WORKDIR /home/tutorial/app

COPY package*.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD node index.js
