![Build Docker images](https://github.com/philips-software/docker-node/workflows/Build%20Docker%20images/badge.svg)
[![Slack](https://philips-software-slackin.now.sh/badge.svg)](https://philips-software-slackin.now.sh)

# Docker images

This repo will contain docker images with node

Current versions available:
```
.
├── 10
│   ├── java
│   │   └── Dockerfile
│   └── vanilla
│       └── Dockerfile
├── 12
│   ├── java
│   │   └── Dockerfile
│   └── vanilla
│       └── Dockerfile
├── 14
│   ├── java
│   │   └── Dockerfile
│   └── vanilla
│       └── Dockerfile
```
## Usage

Images can be found on [https://hub.docker.com/r/philipssoftware/node/](https://hub.docker.com/r/philipssoftware/node/).

```
docker run philipssoftware/node:lts node --version
docker run philipssoftware/node:12-java node --version && java -version
```

## Content

The images obviously contain nodeJS, but also two other files:
- `REPO`
- `TAGS`

### REPO

This file has a url to the REPO with specific commit-sha of the build.
Example: 

```
$ docker run philipssoftware/node:12 cat REPO
https://github.com/philips-software/docker-node/tree/facb2271e5a563e5d6f65ca3f475cefac37b8b6c
```

### TAGS

This contains all the similar tags at the point of creation. 

```
$ docker run philipssoftware/node:12 cat TAGS
node node:stable node:12 node:12.18 node:12.18.3 node:12.18.3-stretch
```

You can use this to pin down a version of the container from an existing development build for production. When using `node:11` for development. This ensures that you've got all security updates in your build. If you want to pin the version of your image down for production, you can use this file inside of the container to look for the most specific tag, the last one.

## Simple Tags

### nodeJS stable
- `node` `node:stable` `node:14` `node:14.10` `node:14.10.0` `node:14.10.0-stretch` [14/vanilla/Dockerfile](14/vanilla/Dockerfile)

### nodeJS lts
- `node:lts` `node:12` `node:12.18` `node:12.18.3` `node:12.18.3-stretch` [12/vanilla/Dockerfile](12/vanilla/Dockerfile)

### nodeJS 10
- `node:10` `node:10.22` `node:10.22.0` `node:10.22.0-stretch` [10/vanilla/Dockerfile](10/vanilla/Dockerfile)

### nodeJS stable with openjdk
- `node:java` `node:stable-java` `node:14-java` `node:14.10-java` `node:14.10.0-java` `node:14.10.0-stretch-java` [14/java/Dockerfile](14/java/Dockerfile)`

### nodeJS lts with openjdk
- `node:lts-java` `node:12-java` `node:12.18-java` `node:12.18.3-java` `node:12.18.3-stretch-java` [12/java/Dockerfile](12/java/Dockerfile)

### nodeJS 10 with openjdk
- `node:10-java` `node:10.22-java` `node:10.22.0-java` `node:10.22.0-stretch-java` [10/java/Dockerfile](10/java/Dockerfile)
        

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
