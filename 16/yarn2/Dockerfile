FROM node:16.14.0-buster-slim
LABEL maintainer="Forest Keepers <Jeroen.knoops@philips.com>"

RUN apt-get update && \
    apt-get install -y \
      curl \
      jq \
      git \
      wget \
      openssl \
      bash \
      tar \
      net-tools && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir /app

RUN yarn set version 3.1.0 && \
    npm install --g lerna

WORKDIR /app

ADD REPO TAGS /app/

RUN echo '[ ! -z "$TERM" -a -r /etc/motd ] && cat /etc/motd' \
    >> /etc/bash.bashrc \
    ; echo "\
----------------------------------------------------------------------------------------------\n\
TAGS: $(cat /app/TAGS)\n\
REPO: $(cat /app/REPO)\n\
----------------------------------------------------------------------------------------------\n\
NODE: $(node --version)\n\
NPM: $(npm --version)\n\
YARN: $(yarn --version)\n\
----------------------------------------------------------------------------------------------"\
    > /etc/motd

# Define default command.
CMD ["/bin/bash"]
