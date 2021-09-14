FROM node:14.17.6-buster-slim
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

RUN yarn set version latest && \
    yarn global add lerna

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
----------------------------------------------------------------------------------------------"\
    > /etc/motd

# Define default command.
CMD ["/bin/bash"]
