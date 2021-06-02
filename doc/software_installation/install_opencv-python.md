## requirements for installing opency-python via pip


```zsh
$sudo apt install build-essential cmake git pkg-config libgtk-3-dev "libcanberra-gtk*"
```

```zsh
$sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev
```

```zsh
$sudo apt install libjpeg-dev libpng-dev libtiff-dev gfortran openexr libatlas-base-dev opencl-headers
```

```zsh
$sudo apt install libtbb2 libtbb-dev libdc1394-22-dev
```

This step will take some time. My raspberry pi 3 take more than 1.5 hours.
```zsh
$pip install opencv-python
```

Check
```zsh
$python
Python 3.6.6 | packaged by rpi | (default, Sep  6 2018, 10:56:14) 
[GCC 6.3.0 20170516] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import cv2

```
