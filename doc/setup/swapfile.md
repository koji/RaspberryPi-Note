# Swap file

Probably you may need this step for installing OpenCV on your pi          

```zsh
$ sudo vim /etc/dphys-swapfile
default 100MB --> 1024
$ sudo /etc/init.d/dphys-swapfile stop
$ sudo /etc/init.d/dphys-swapfile start
$ free -m 
                total        used        free      shared  buff/cache   available
Mem:            875          65         378          11         431         747
Swap:          1023           0        1023
```
