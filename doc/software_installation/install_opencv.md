# Install OpenCV3

```zsh
#　Remove previous version
sudo apt autoremove libopencv3
# Install 
wget https://github.com/mt08xx/files/raw/master/opencv-rpi/libopencv3_3.4.3-20180907.1_armhf.deb
sudo apt install -y ./libopencv3_3.4.3-20180907.1_armhf.deb
sudo ldconfig
```

