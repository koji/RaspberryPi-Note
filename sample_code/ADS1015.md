#### Pin
VDD --> 3.3V pin 1  
GND --> GND  pin 6  
SCL --> SCL  pin 5 
SDA --> SDA  pin 3

potentiometer/tmp36 --> A0  


#### Enable I2C
```zsh
$ sudo raspi-config

Enable I2C

```


https://github.com/adafruit/Adafruit_Python_ADS1x15


```zsh
koji@devpi:~/analog/Adafruit_Python_ADS1x15/examples $ sudo /home/koji/.pyenv/shims/python simpletest.py
Reading ADS1x15 values, press Ctrl-C to quit...
|      0 |      1 |      2 |      3 |
-------------------------------------
|      0 |      0 |      0 |      0 |
|      0 |      0 |      0 |      0 |
|      0 |      0 |      0 |      0 |
|      0 |      0 |      0 |      0 |
|      0 |      0 |      0 |      0 |

```



https://learn.adafruit.com/adafruit-16-channel-servo-driver-with-raspberry-pi/configuring-your-pi-for-i2c

```zsh
koji@devpi:~/analog/Adafruit_Python_ADS1x15/examples $ sudo i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f
10: 10 11 12 13 14 15 16 17 18 19 1a 1b 1c 1d 1e 1f
20: 20 21 22 23 24 25 26 27 28 29 2a 2b 2c 2d 2e 2f
30: 30 31 32 33 34 35 36 37 38 39 3a 3b 3c 3d 3e 3f
40: 40 41 42 43 44 45 46 47 48 49 4a 4b 4c 4d 4e 4f
50: 50 51 52 53 54 55 56 57 58 59 5a 5b 5c 5d 5e 5f
60: 60 61 62 63 64 65 66 67 68 69 6a 6b 6c 6d 6e 6f
70: 70 71 72 73 74 75 76 77
```


### Trouble shooting
```zsh
$ sudo apt-get install i2c-tools
$ sudo reboot
$ sudo i2cdetect -y 1

add item to /etc/modules

$ sudo vim /etc/modules
add the followings

i2c-bcm2708
i2c-dev

# sudo raspi-config
I2C disable --> enable

koji@devpi:~/analog $ sudo i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- 48 -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --

```

I borrowed saleae I2C analyzer.  
![saleae I2C analyzer](https://github.com/sleepy-maker/Connected-Devices/blob/master/raspberry_pi_analog_test/device.jpg)   
  
    
![saleae I2C analyzer software](https://github.com/sleepy-maker/Connected-Devices/blob/master/raspberry_pi_analog_test/analyzer.png)

http://downloads.saleae.com/specs/Logic+8+Data+Sheet.pdf  


### potentiometer
![potentiometer](https://github.com/sleepy-maker/Connected-Devices/blob/master/raspberry_pi_analog_test/raspberrypi_analog_io.gif)


### TMP36
```zsh
formula from Adafruit
Voltage at pin in milliVolts = (reading from ADC) * (3300/1655)
Centigrade temperature = [(analog voltage in mV) - 500] / 10 F
```

