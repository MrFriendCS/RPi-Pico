# RGB LED

Using Picozero to to sense a button press to control a RGB LED.

## Layout

![RGB LED Layout](media/rgbButton.png)

## Code

``` python
# Import code
from picozero import RGBLED
from time import sleep

# Pins for RGB LED
rgb = RGBLED(13, 14, 15)

# Declare RGB Colours
black = (0, 0, 0)  # All off
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
white = (255, 255, 255)  # All on

# Declare array
colours = [red, green, blue, white, black]

# Loop forever
while True:
    
    # Show each colour in turn
    for colour in colours:
        rgb.color = colour
        sleep(0.5)
    
    # Get brighter
    for counter in range(256):
        rgb.color = (counter, counter, counter)
        sleep(0.005)
    
    # Get dimmer
    for counter in range(256):
        rgb.color = (255-counter, 255-counter, 255-counter)
        sleep(0.005)
        
    sleep(0.5)
 ```
 
