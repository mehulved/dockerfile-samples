FROM node:lts-buster as node_modules_build

RUN groupadd tutorial && useradd --no-log-init -r -g tutorial tutorial

WORKDIR /home/tutorial

RUN mkdir app

WORKDIR /home/tutorial/app

COPY package*.json .

RUN npm install

FROM node:lts-alpine as final_image

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.tutorial.webapi.version="0.3"

RUN addgroup -S tutorial && adduser -S tutorial -G tutorial

WORKDIR /home/tutorial

RUN mkdir app

WORKDIR /home/tutorial/app

COPY --from=node_modules_build /home/tutorial/app/node_modules ./node_modules

COPY . .

EXPOSE 3000

CMD node index.js
