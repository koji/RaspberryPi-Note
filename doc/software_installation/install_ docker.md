# Docker

## why do we need to use Docker
Using Docker is completely optional, but Docker helps users to keep dev environment on Raspberry Pi very clean.  
Thi means a lot to devs.

## install docker
```
# install
$ curl -sSL https://get.docker.com/ | sh

# check version
$ sudo docker -v

# add user
$ sudo usermod -aG docker pi

# add settings
$ sudo systemctl enable docker
```


## run docker
You don't need to use `sudo` because we have added a user to the group
```
$ docker run --name rpi-raspbian-stretch -ti --privileged resin/rpi-raspbian:stretch /bin/bash
```
