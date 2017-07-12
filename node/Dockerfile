# Set the base image to Ubuntu
FROM node:0.10-onbuild

# File Author / Maintainer
MAINTAINER Mukta Aphale aMukta@gmail.com

# Install Node.js and other dependencies
#RUN apt-get update
#RUN apt-get -y install curl 
#RUN curl -sL https://deb.nodesource.com/setup | bash -
#RUN    apt-get -y install python build-essential nodejs
#RUN apt-get install -y npm

# Install nodemon
RUN npm install -g nodemon

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

# Define working directory
WORKDIR /src
ADD . /src

# Expose port
EXPOSE  9090

# Run app using nodemon
CMD ["nodemon", "/src/index.js"]
