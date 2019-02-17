# openFrameworks

## update Pi
```
$ sudo apt-get update -y
```

## install git
```
$ sudo apt-get install -y git
```

## download & install openFrameworks
this step takes some time    

```
$ cd ~/
$ git clone --depth=1 https://github.com/openFrameworks/openFrameworks.git
$ cd ~/openFrameworks/scripts/linux/debian
$ yes | sudo ./install_dependencies.sh
$ yes | sudo ./install_codecs.sh

$ cd ~/openFrameworks/scripts/linux/
$ yes | sudo ./download_libs.sh
$ make Release -C ~/openFrameworks/libs/openFrameworksCompiled/project
```

## test sample
```
$ cd ~/openFrameworks/examples/graphics/polygonExample/
$ cp ~/openFrameworks/scripts/templates/linuxarmv6l/Makefile ./
$ make
$ make run
```
