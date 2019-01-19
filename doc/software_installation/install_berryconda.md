# Install Berryconda

Berryconda  
https://github.com/jjhelmus/berryconda    
   
   
```
# download berryconda
$ wget https://github.com/jjhelmus/berryconda/releases/download/v2.0.0/Berryconda3-2.0.0-Linux-armv7l.sh
$ chmod +x Berryconda3-2.0.0-Linux-armv7l.sh
$ ./Berryconda3-2.0.0-Linux-armv7l.sh
```
## create virtual env
```
$ conda create --name mlenv python=3.6
```

## activate/deactivate virtual env
```
$ source activate mlenv

you will see something like the following
(mlenv) piuser@raspberrypi:~ $

$ source deactivate

```
