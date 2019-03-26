FROM node:11.12.0-stretch 
MAINTAINER Forest Keepers <Jeroen.knoops@philips.com>

RUN apt-get update && \
    apt-get install \
      curl \
      jq \
      git \
      wget \
      openssl \
      bash \
      net-tools && \
    rm -rf /var/lib/apt/lists/*

RUN addgroup -S node && \
  adduser -S -G node node 

RUN mkdir /app
RUN chown node:node /app

USER node

WORKDIR /app

ADD REPO .
ADD TAGS .

# Define default command.
CMD ["/bin/bash"]
