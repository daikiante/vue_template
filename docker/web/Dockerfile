FROM node:14.15.0-alpine
WORKDIR /app
RUN apk update && apk upgrade
RUN apk add git
RUN apk add --update nodejs npm && \
    npm install -g vue-cli && \
    cd ~/app &&\
    vue init webpack app &&\
    cd app &&\
    npm run dev