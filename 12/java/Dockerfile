FROM node:12.9.0-stretch
MAINTAINER Forest Keepers <Jeroen.knoops@philips.com>

RUN apt-get update && \
    apt-get install -y \
      curl \
      jq \
      git \
      wget \
      openssl \
      bash \
      net-tools \
      default-jdk && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir /app
RUN chown node:node /app

USER node

WORKDIR /app

ADD REPO .
ADD TAGS .

# Define default command.
CMD ["/bin/bash"]
