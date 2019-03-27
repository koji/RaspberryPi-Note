```
$ sudo /etc/init.d/ssh status
```

If you get errors like `Could not load host key`

```
$ sudo rm -f /etc/ssh/ssh_host*
$ sudo dpkg-reconfigure openssh-server
```
