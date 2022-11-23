# Weatherapp

To complete the prerequisites, a personal API key has been created:
658d9d99e91f7f79e9dacaab32d00f4a

Both applications can be run and started locally from frontend and backend folders. Make sure to instal node and npm beforehand.

Command to start the applications from both folders:
npm start

If application should be executable in Windows, make sure to modify package.json 12th line in fronted application:

from   
"start": "node_modules/.bin/webpack-dev-server --config webpack.config.js --progress --inline --colors",
to    
"start": node node_modules/bin/webpack-dev-server.js --config webpack.config.js --progress --inline --colors",

Both applications are contenerized.
Backend application can be build and run with following commands in backend folder based on the created Dockerfile:

docker build -t backend:dev .
docker run -d -p 9000:9000 backend:dev

For frontend application that was required to add ENV NODE_OPTIONS=--openssl-legacy-provider variable to fix SSL issue.
Frontend application can be build and run with with following commands in frontend folder based on the created Dockerfile:

docker build -t frontend:dev .
docker run -d -p 8000:8000 frontend:dev

To connect both applications and test the application in whetherapp folder run following command:

docker-compose up

Make sure to modify ENDPOINT: http://xxx:9000/api (i.e. localhost) in docker-compose.yml and APPID can replaced by personal key to customize the application. 
Make sure to use http://xxx:8000 URL to open the application.

I've already created the application which is Cloud based and you can open it with following URL:
http://ec2-44-203-121-60.compute-1.amazonaws.com:8000/

There are attached 2 ansible playbooks to which allowed me to install docker and application.
