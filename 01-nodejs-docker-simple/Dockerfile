FROM node:lts-buster

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.tutorial.webapi.version="0.1"

RUN groupadd tutorial && useradd --no-log-init -r -g tutorial tutorial

WORKDIR /home/tutorial

RUN mkdir app

WORKDIR /home/tutorial/app

COPY . .

RUN npm install

EXPOSE 3000

CMD node index.js
