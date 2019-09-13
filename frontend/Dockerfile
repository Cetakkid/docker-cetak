# Pull base image

FROM node:lts-alpine

RUN npm install -g -http-server

# Working directory
WORKDIR /frontend
ENV PATH /frontend/node_modules/.bin:$PATH

# Copy package json file
COPY package*.json ./

RUN npm install 

COPY . .

RUN npm run build

EXPOSE 8080
CMD [ "http-server", "dist" ]