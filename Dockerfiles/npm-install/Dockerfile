FROM node:12
# FROM node:12.16-stretch

# Create app directory
# WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
# COPY package*.json ./

# Copy all static assets.
RUN rm -rf /home/sourcecode && \
mkdir /home/sourcecode && \
printf "\n STARTING COPY SOURCECODE... \n"

COPY . /home/sourcecode

RUN printf "" && \
printf "\n ------------------------ " && \
printf "\n  NODE VERSION: %s" $(node -v) && \
printf "\n  NPM VERSION:  %s" $(npm -v) && \
printf "\n ------------------------ \n" && \
cd /home/sourcecode && \
printf "\n STARTING NPM INSTALL... \n" && \
npm install && \
# If you are building for production use:
# npm ci --only=production
printf "\n STARTING NPM TEST... \n" && \
npm test

# Bundle app source
# COPY . .

# EOF #

