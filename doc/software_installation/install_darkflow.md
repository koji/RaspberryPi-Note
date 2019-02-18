# darkflow

## requirements
tensorflow   
opencv 
cython     

## install darkflow
```
$ git clone https://github.com/thtrieu/darkflow.git
$ cd darkflow
$ python3 setup.py build_ext --inplace
```

## install libs
```
$ sudo apt-get -y install libatlas-base-dev
$ sudo apt-get -y install libjasper-dev
$ sudo apt-get install libqtgui4
$ sudo apt-get -y install libqt4-test
```

## get weight and config
```
$ wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights
$ mkdir bin
$ mv yolov2-tiny-voc.weights ./bin/

$ wget https://raw.githubusercontent.com/pjreddie/darknet/master/cfg/yolov2-tiny-voc.cfg
$ mv yolov2-tiny-voc.cfg ./cfg/
```

## edit misc.py
```python
import pickle
import numpy as np
import cv2
import os

labels20 = ["aeroplane", "bicycle", "bird", "boat", "bottle",
    "bus", "car", "cat", "chair", "cow", "diningtable", "dog",
    "horse", "motorbike", "person", "pottedplant", "sheep", "sofa",
    "train", "tvmonitor"]

# 8, 14, 15, 19

voc_models = ['yolo-full', 'yolo-tiny', 'yolo-small',  # <- v1
              'yolov1', 'tiny-yolov1', # <- v1.1
              'tiny-yolo-voc', 'yolo-voc', 'yolov2-tiny-voc'] # <- v2

coco_models = ['tiny-coco', 'yolo-coco',  # <- v1.1
               'yolo', 'tiny-yolo', 'yolov2-tiny-voc'] # <- v2

coco_names = 'coco.names'
nine_names = '9k.names'
```
After this, need to reboot pi   

## create test.py
```python
from darkflow.net.build import TFNet
import cv2

options = {"model": "cfg/yolov2-tiny-voc.cfg", "load": "bin/yolov2-tiny-voc.weights", "threshold": 0.1}
tfnet = TFNet(options)
```

