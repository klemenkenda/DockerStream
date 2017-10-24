# Installation

## Prerequisites

* Ubuntu 17.10, server, with OpenSSH, tmux.

## Docker

```
sudo apt install docker
```

## Docker Machine

```
curl -L https://github.com/docker/machine/releases/download/v0.13.0/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine &&
chmod +x /tmp/docker-machine &&
sudo cp /tmp/docker-machine /usr/local/bin/docker-machine
```

