![Build Docker images](https://github.com/philips-software/docker-node/workflows/Build%20Docker%20images/badge.svg)
[![Slack](https://philips-software-slackin.now.sh/badge.svg)](https://philips-software-slackin.now.sh)

# Docker images

This repo will contain docker images with node

Current versions available:
```
.
├── 14
│   ├── java
│   │   └── Dockerfile
│   └── vanilla
│       └── Dockerfile
├── 16
│   ├── java
│   │   └── Dockerfile
│   ├── vanilla
│   │   └── Dockerfile
│   └── yarn2
│       └── Dockerfile
├── 17
│   ├── java
│   │   └── Dockerfile
│   ├── vanilla
│   │   └── Dockerfile
│   └── yarn2
│       └── Dockerfile
```
## Usage

Images can be found on [https://hub.docker.com/r/philipssoftware/node/](https://hub.docker.com/r/philipssoftware/node/).

```
docker run philipssoftware/node:lts node --version
docker run philipssoftware/node:14-java node --version && java -version
```

## Content

The images obviously contain nodeJS, but also two other files:
- `REPO`
- `TAGS`

### REPO

This file has a url to the REPO with specific commit-sha of the build.
Example:

```
$ docker run philipssoftware/node:14 cat REPO
https://github.com/philips-software/docker-node/tree/facb2271e5a563e5d6f65ca3f475cefac37b8b6c
```

### TAGS

This contains all the similar tags at the point of creation.

```
$ docker run philipssoftware/node:14 cat TAGS
node node:stable node:14 node:14.19.1 node:14.19.1 node:14.19.1-stretch
```

You can use this to pin down a version of the container from an existing development build for production. When using `node:11` for development. This ensures that you've got all security updates in your build. If you want to pin the version of your image down for production, you can use this file inside of the container to look for the most specific tag, the last one.

### Node and Java version

If you want to know the version of Node (or Java if available), you can do the following:

```
$ docker run -it philipssoftware/node:12
```

## LTS & STABLE

Currently 17.0.1 is supposed to be the Stable version of Node, but due to an error in OpenSSL 3.x we cannot use it together with the GitHub checkout action. Therefore we've pointed Stable to LTS in order to not break the latest version of the node image.

## Simple Tags

### nodeJS lts / stable
- `node` `node:stable` `node:lts` `node:16` `node:16.15` `node:16.15.0` `node:16.15.0-buster` [lts/vanilla/Dockerfile](lts/vanilla/Dockerfile)

### nodeJS current
- `current` `node:17` `node:17.9` `node:17.9.0` `node:17.9.0-buster` [current/vanilla/Dockerfile](current/vanilla/Dockerfile)

### nodeJS 14 - not recommended (use `stable` or `lts`)
- `node:14` `node:14.19` `node:14.19.1` `node:14.19.1-buster-slim` [14/vanilla/Dockerfile](14/vanilla/Dockerfile)

## Tags with yarn2

### nodeJS lts / stable - Yarn 2
- `node:yarn2` `node:stable-yarn2` `node:lts-yarn2` `node:16-yarn2` `node:16.15-yarn2` `node:16.15.0-yarn2` `node:16.15.0-buster-yarn2` [lts/yarn2/Dockerfile](lts/yarn2/Dockerfile)

### nodeJS current - Yarn 2
-  `node:current-yarn2` `node:17-yarn2` `node:17.9-yarn2` `node:17.9.0-yarn2` `node:17.9.0-buster-yarn2` [current/yarn2/Dockerfile](current/yarn2/Dockerfile)

## Tags with openjdk

### nodeJS lts / stable with openjdk
- `node:java` `node:stable-java` `node:lts-java` `node:16-java` `node:16.15-java` `node:16.15.0-java` `node:16.15.0-buster-java` [lts/java/Dockerfile](lts/java/Dockerfile)`

### nodeJS current with openjdk
- `node:current-java` `node:17-java` `node:17.9-java` `node:17.9.0-java` `node:17.9.0-buster-java` [current/java/Dockerfile](current/java/Dockerfile)`

### nodeJS 14 with openjdk - not recommended (use `stable` or `lts`)
- `node:14-java` `node:14.19-java` `node:14.19.1-java` `node:14.19.1-buster-slim-java` [14/java/Dockerfile](14/java/Dockerfile)

## Why

> Why do we have our own docker image definitions?

We often need some tools in a container for checking some things. F.e. [jq](https://stedolan.github.io/jq/), [aws-cli](https://aws.amazon.com/cli/) and [curl](https://curl.haxx.se/).
We can install this every time we need a container, but having this baked into a container seems a better approach.

That's why we want our own docker file definitions.

## Issues

- If you have an issue: report it on the [issue tracker](https://github.com/philips-software/docker-node/issues)

## Author

- Jeroen Knoops <jeroen.knoops@philips.com>
- Niek Palm <niek.palm@philips.com>

## License

License is MIT. See [LICENSE file](LICENSE.md)

## Philips Forest

This module is part of the Philips Forest.

```
                                                     ___                   _
                                                    / __\__  _ __ ___  ___| |_
                                                   / _\/ _ \| '__/ _ \/ __| __|
                                                  / / | (_) | | |  __/\__ \ |_
                                                  \/   \___/|_|  \___||___/\__|

                                                                 Infrastructure
```

Talk to the forestkeepers in the `docker-images`-channel on Slack.

[![Slack](https://philips-software-slackin.now.sh/badge.svg)](https://philips-software-slackin.now.sh)
