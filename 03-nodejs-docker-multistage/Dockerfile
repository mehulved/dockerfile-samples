FROM node:lts-buster as node_modules_build

RUN groupadd slashrtc && useradd --no-log-init -r -g slashrtc slashrt

WORKDIR /home/slashrtc

RUN mkdir app

WORKDIR /home/slashrtc/app

COPY package*.json .

RUN npm install

FROM node:lts-alpine as final_image

LABEL maintainer="mehul.n.ved@gmail.com"

LABEL in.slashrtc.webapi.version="0.3"

RUN addgroup -S slashrtc && adduser -S slashrtc -G slashrtc

WORKDIR /home/slashrtc

RUN mkdir app

WORKDIR /home/slashrtc/app

COPY --from=node_modules_build /home/slashrtc/app/node_modules ./node_modules

COPY . .

EXPOSE 3000

CMD node index.js
