FROM node:19-alpine
ENV NODE_OPTIONS=--openssl-legacy-provider
WORKDIR /app
COPY package.json /app
RUN npm install
COPY /src /app/src
COPY webpack.config.js /app
CMD npm start
EXPOSE 8000