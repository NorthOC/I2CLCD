# Use screens with Python Raspberry Pico

## Install

Copy `lcd_api.py` into your working directory.

## How to use

``` Python
import utime
from machine import Pin,I2C
from lcd_api import I2CLCD

I2C_ADDR     = 0x27
I2C_NUM_ROWS = 2
I2C_NUM_COLS = 16

# SDA - PIN 0
# SCL - PIN 1
sda = machine.Pin(0)
scl = machine.Pin(1)

# INIT LCD DISPLAY
i2c = I2C(0, sda=sda, scl=scl, freq=400000)
lcd = I2CLCD(i2c, I2C_ADDR, I2C_NUM_ROWS, I2C_NUM_COLS)    

#PRINT
utime.sleep(1)
lcd.clear()
lcd.move_to(0,0)
lcd.putstr(f"Pico LCD {a}")
lcd.move_to(0,1)
lcd.putstr("Tutorial")

```