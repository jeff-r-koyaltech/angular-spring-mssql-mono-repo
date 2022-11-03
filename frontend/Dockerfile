
FROM node:18-slim

# this dockerfile is intended for dev use cases
ENV NODE_ENV=development

WORKDIR /home/app

COPY package.json package.json
COPY yarn.lock yarn.lock

RUN yarn install

COPY src src
COPY angular.json angular.json
COPY *.conf.js ./
COPY tsconfig* ./

# web server
EXPOSE 4200

# Karma server (TODO - would we use this?)
EXPOSE 9876

CMD yarn run start --host=0.0.0.0

