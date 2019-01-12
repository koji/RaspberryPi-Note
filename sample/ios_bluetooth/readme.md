# Bluetooth(Peripheral) 

In this case, iOS=Central and pi=Peripheral

## Install libs
```zsh
$ sudo apt-get update
$ sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
$ sudo apt-get install libdbus-1-dev libdbus-glib-1-dev libglib2.0-dev libical-dev
```

## Install nodejs via n
There are a couple of options to install nodejs. apt-get/nodebrew/nvm/source code. This sample uses `n` (https://github.com/tj/n)
```zsh
$ sudo apt-get install curl
$ curl -L https://git.io/n-install | bash
# need to set PATH
$ ~/.bashrc or ~/.zshrc
$ n 9.11.2
```

## Install bleno
```zsh
$ npm -v
5.6.0
$ mkdir iosandpibluetooth
$ cd iosandpibluetooth/
$ npm init -y
$ npm install bleno --save
```
