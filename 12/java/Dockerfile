FROM node:12.19.0-stretch
LABEL maintainer="Forest Keepers <Jeroen.knoops@philips.com>"

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

RUN yarn global add lerna

WORKDIR /app

ADD REPO .
ADD TAGS .

# Define default command.
CMD ["/bin/bash"]
