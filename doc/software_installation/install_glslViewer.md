Basically, you just need to follow this repository.  
https://github.com/patriciogonzalezvivo/glslViewer  

Then run the following command  
```
$ cd example
$ glslViewer test.frag
```

If you get `failed to open vchiq instance`, there are 2 ways to solve the issue.
1. add your user to `video` group. After hit the command, you will need to reboot your pi
```
$ sudo usermod -a -G video <your username>
```
2. run the command with `sudo`
```
$ sudo glslViewer test.frag
```
