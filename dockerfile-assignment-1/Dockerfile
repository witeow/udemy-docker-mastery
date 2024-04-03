# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:6-alpine
# node image version as instructed in README.md

EXPOSE 3000
# this app listens on port 3000, but the container should launch on port 80

RUN apk add --no-cache tini
# using alpine manager to install tini

WORKDIR /usr/src/app
# change working directory to the app folder

COPY package.json package.json
# copy in package.json file to run npm install

RUN npm install \
# run npm install to install dependencies from package.json
    && npm cache clean --force

COPY . .
# all files in current direcotry to image

CMD ["/sbin/tini", "--", "node", "./bin/www"]
# use CMD  to start container