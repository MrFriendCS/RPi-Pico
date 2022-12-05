# Neopixels

Using Picozero to control a strip of Neopixels.

## Layout

![Servo Layout](media/neopixel.png)

## Code

``` python
import time
from neopixel import Neopixel
# https://github.com/blaz-r/pi_pico_neopixel

# Kitronik ZIP Stick, 35129 - 5 LEDS
numpix = 5
mode = "GRB"

gpio = 28

pixels = Neopixel(numpix, 0, gpio, mode)
  
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
yellow = (225, 225, 0)
cyan = (0, 255, 255)
black = (0, 0, 0)
white = (255, 255, 255)

pixels.brightness(25)

colours = [red, yellow, green, cyan, blue]

while True:
    
    # Turn each LED on - various colours
    for index in range(5):
        pixels.set_pixel(index, colours[index])
        pixels.show()
        time.sleep(1)
    
    # Rotate right 5 times
    for counter in range(5):
        pixels.rotate_right()
        pixels.show()
        time.sleep(1)
    
    # Rotate left 5 times
    for counter in range(5):
        pixels.rotate_left()
        pixels.show()
        time.sleep(1)
    
    # Turn each LED white (fully on)
    for index in range(5):
        pixels.set_pixel(index, white)
        pixels.show()
        time.sleep(1)
    
    # Turn each LED black (fully off)
    for index in range(5):
        pixels.set_pixel(4-index, black)
        pixels.show()
        time.sleep(1)
```
