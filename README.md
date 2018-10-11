# alpine-pkg-py-pandas

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-py-pandas/tree/master.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-py-pandas/tree/master)

This is the Python [pandas][pandas] package as an Alpine Linux package.

## Releases

See the [releases page](https://github.com/sgerrand/alpine-pkg-py-pandas/releases) for the latest
download links.

## Installing

The current installation method for these packages is to install them with `apk`:

    wget --quiet --output-document=/etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    apk add --no-cache --repository=https://apkproxy.herokuapp.com/sgerrand/alpine-pkg-py-pandas py-pandas=0.23.4-r0

[pandas]: https://pandas.pydata.org/
