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
    
    # Flash LEDs on and off
    for counter in range(5):
        # Turn all LEDs white (fully on)
        pixels.fill(white)
        pixels.show()
        time.sleep(0.5)
        
        # Turn all LEDs black (fully off)
        pixels.fill(black)
        pixels.show()
        time.sleep(0.5)
```
