# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project uses the version of main tool as main version number .

### Changed
- v12.22.8 / v14.18.2 / v16.13.1 (LTS/stable) / v17.3.0 (current)
- Add `current` to 17.1.0
- Currently 17.0.1 is supposed to be the Stable version of Node, but due to an error in OpenSSL 3.x we cannot use it together with the GitHub checkout action. Therefore we've pointed Stable to LTS in order to not break the latest version of the node image.
- v12.22.7 / v14.18.1 / v16.13.0 (LTS) / v17.0.1 (Stable)
- v12.22.6 / v14.17.6 / v15.14.0 / v16.9.1
- Add yarn2 version 
- v12.22.5 / v14.17.5 / v15.14.0 / v16.7.0
- Add 16 as stable
- v12.22.1 / v14.16.1 / v15.14.0
- Updated versions
- Use buster in stead of stretch
- lts --> 14.15.3
- lts --> 14.15.2
- lts --> 14.15.0
- stable --> 15.1.0
- Update version to 15.0.0-stretch
- Update version to 14.14.0-stretch
- Add lerna
- Remove USER node. GitHub actions requires root in order to do a checkout.
- Update version to 14.13.1-stretch
- Update version to 14.13.0-stretch
- Update version to 14.12.0-stretch
- Update version to 12.18.4-stretch
- Update version to 10.22.1-stretch
- Update version to 14.11.0-stretch
- Update version to 14.10.1-stretch
- Update version to 14.10.0-stretch
- Dependabot automatic updates dependencies
- Update versions 10, lts and stable to 10.22.0, 12.18.3, 14.7.0
- Update versions 10, lts and stable to 10.20.1, 12.16.3, 14.0.0
- [#14] - Update stable versions
- [#12] - Update lts versions
- Use docker-ci-scripts actions
- [#9] - Add prefix docker- in repository name
- (ci) Fixes small typo in greetings message
- (ci) Uses Github Action instead of travis-ci
- Better Actions workflow 
- node:lts --> 10.16.3
- node:stable --> 12.9.0
- Uses Github Actions instead of travis-ci
- Adds node:11.12.0-stretch with and without openjdk 8

[#14]: https://github.com/philips-software/docker-node/issues/14
[#12]: https://github.com/philips-software/docker-node/issues/12
[#9]: https://github.com/philips-software/docker-node/issues/9
