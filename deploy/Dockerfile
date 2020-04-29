FROM node:12.16.3

WORKDIR /usr/src/app

RUN mkdir client
RUN mkdir server

WORKDIR /usr/src/app/client

COPY client/package*.json ./

RUN npm install

COPY client .

RUN npm run build

WORKDIR /usr/src/app/server

COPY server/package.json ./

RUN npm install

COPY server .

EXPOSE 8080
CMD ["node", "src/index.js"]