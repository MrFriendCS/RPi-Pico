# Servo

Using Picozero to control a servo.

## Layout

![Servo Layout](media/servo.png)

## Code

``` python
from picozero import Servo
from time import sleep

servo = Servo(1)

servo.min()
sleep(1)

servo.mid()
sleep(1)

servo.max()
sleep(1)

servo.off()
```
