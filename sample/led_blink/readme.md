
![](https://github.com/orz-orz-orz-orz-orz/pi-setup/blob/master/sample/images/gpio.png)

### Install RPi.GPIO
https://pypi.python.org/pypi/RPi.GPIO

```shell
$ pip install RPi.GPIO
```
##### python
```python
from time import sleep
import RPi.GPIO as GPIO


GPIO.setmode(GPIO.BOARD)
led = 11
button1 = 12

def setupEnv():                
    # init buttons
    GPIO.setup(button1, GPIO.IN, pull_up_down=GPIO.PUD_UP)
    GPIO.setup(led, GPIO.OUT)


# call setup
setupEnv()

while(1):
    # press the button 1
    if GPIO.input(button1) == 0:
        GPIO.output(led, GPIO.HIGH)
        print("button1 was pressed")
        #GPIO.output(button1,True)
        sleep(.5)
    else:
        GPIO.output(led,GPIO.LOW)


```
