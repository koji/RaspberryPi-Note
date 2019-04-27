## Update pip
```
$ pip3 install pip -U
```

If you get errors from the above command, there 2 things you should try.

1. use `sudo` with pip3

```
$ sudo pip3 install pip -U
```

If still you have issue, you can extend the swap file size.  
```
$ sudo vim /etc/dphys-swapfile
CONF_SWAPSIZE=2048

$ sudo /etc/init.d/dphys-swapfile restart swapon -s

```

Then try install command again!  
