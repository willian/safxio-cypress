FROM node:8
MAINTAINER SAF Platform <info@safplatform.com>

RUN apt-get update \
  && apt-get install -y \
    libgtk2.0-0 \
    libnotify-dev \
    libgconf-2-4 \
    libnss3 \
    libxss1 \
    libasound2 \
    xvfb

RUN apt-get install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common \
  && curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - \
  && add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" \
  && apt-get update \
  && apt-get install -y docker-ce jq \
  && curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose \
  && chmod +x /usr/local/bin/docker-compose

RUN npm install -g npm@6.4.1 \
  && npm install -g cypress --unsafe-perm --silent \
  && npm install -g wait-on --unsafe-perm --silent

# versions of local tools
RUN node -v
RUN npm -v
RUN yarn -v
