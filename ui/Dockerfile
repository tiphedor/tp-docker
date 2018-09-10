FROM node:8-slim

CMD mkdir /app
WORKDIR /app

COPY package.json .
RUN npm install

COPY src src
CMD node src/server.js

EXPOSE 3000
