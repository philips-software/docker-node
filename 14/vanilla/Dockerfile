FROM node:16.1.0-buster-slim
LABEL maintainer="Forest Keepers <Jeroen.knoops@philips.com>"

RUN apt-get update && \
    apt-get install -y \
      curl \
      jq \
      git \
      wget \
      openssl \
      bash \
      net-tools && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir /app && \
    chown node:node /app

RUN yarn global add lerna

WORKDIR /app

ADD REPO .
ADD TAGS .

# Define default command.
CMD ["/bin/bash"]
