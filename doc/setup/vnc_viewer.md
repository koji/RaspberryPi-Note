# VNC Viewer (from Mac)


## pi setting

```zsh
$ sudo raspi-config
# enable
SSH
VNC
Serial Port
Serial Console
```

## Download VNC Viewer
https://www.realvnc.com/en/connect/download/viewer/    

## Check IP address
```zsh
$ ifconfig wlan0
```

Use the IP address to connect via VNC. If you use ufw, you need to open the port, 5900.  
```zsh
$ sudo ufw allow 5900
```
