FROM node:19-alpine
WORKDIR /app
COPY package.json /app
RUN npm install
COPY /src /app
CMD node index.js
EXPOSE 9000