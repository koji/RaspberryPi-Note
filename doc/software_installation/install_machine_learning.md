# Machine Learning Environment

## Install pip
```zsh
$ sudo apt-get install python3-pip
$ pip3 --version
pip 9.0.1 from /usr/lib/python3/dist-packages (python 3.5)
```

## Install TensorFlow
```zsh
$ sudo apt-get install libatlas-base-dev
$ pip3 install --user tensorflow
$ pip3 list | grep tensor
DEPRECATION: The default format will switch to columns in the future. You can use --format=(legacy|columns) (or define a format=(legacy|columns) in your pip.conf under the [list] section) to disable this warning.
tensorboard (1.11.0)
tensorflow (1.11.0)
```

## Install Keras
```zsh
$ sudo apt install libhdf5-serial-dev
$ pip3 install h5py
$ pip3 install keras
```


## Try image classifier
Cloning the repo will take some time.
```zsh
$ git clone https://github.com/tensorflow/models.git
$ cd models/tutorials/image/imagenet
$ python3 classify_image.py

```
