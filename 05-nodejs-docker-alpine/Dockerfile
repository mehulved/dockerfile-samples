FROM node:lts-alpine

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.tutorial.webapi.version="0.5"

RUN addgroup -S tutorial && adduser -S tutorial -G tutorial

WORKDIR /home/tutorial

RUN mkdir app

WORKDIR /home/tutorial/app

COPY package*.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD node index.js
