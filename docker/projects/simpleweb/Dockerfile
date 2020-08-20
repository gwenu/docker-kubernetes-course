# Specify a base image 
FROM node:alpine

WORKDIR /usr/app

# Install some dependencies
COPY ./package.json ./
RUN npm install
COPY ./ ./

# Default command
CMD ["npm", "start"]


#docker run -p 5000:8080 gwenu/docker-simple-app