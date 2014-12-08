micro_PCD8544
=============
PCD8544 driver (Nokia 5110 lcd) for micropython (pyBoard).

This driver uses BitBanging, as I couldn't mkae it work with micro python builtin SPI.

Configuration
-------------

```python
from pcd8544 import PCD8544, BitBangSPI

# below configuration is comaptible with pyBoard SPI channel no. 1
spi = BitBangSPI(
    pyb.Pin('X5', pyb.Pin.OUT_PP), # CS - chip select
    pyb.Pin('X6', pyb.Pin.OUT_PP), # SCK - clock
    pyb.Pin('X8', pyb.Pin.OUT_PP), # MOSI - data to lcd module
)
lcd = PCD8544(spi, 'X3', 'X4')

# you can try to use SPI
# check out how to connect your LCD to SPI here: https://micropython.org/doc/module/pyb/SPI
lcd = PCD8544(1, 'X3', 'X4')
```

Installation
------------
Just copy pcd8544.py file to your pyBoard, and import it in main.py or whatever you want to use it.
