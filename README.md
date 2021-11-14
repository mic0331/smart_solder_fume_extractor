# Smart Solder Fume Extractor

Embeded smart solder fume extractor using HPM particulate metter sensor.

## Problem Statement

Soldering can produce dust and fumes that are hazardous. In addition, using flux containing rosin produces solder fumes that,  
if inhaled, can result in occupational asthma or worsen, existing asthlatic conditions; as well as cause eye and upper respiratour tract irritation.

Fume extractor devices are available cheaply - For basic needs such tools work great however they are noisy and not clever.
if they are not powered on, they simply don’t work.  
Some devices can be controlled by potentiometer to increase or decrease the fan speed however most of them simply run at full speed.

## Smart Solder Fume extractor

Smart fume extractor can automatically detects bad air quality, activate the fan at a speed that corresponds to the level of particulates. Automatically power on/off the device.
They can record the time of execution of the device and predict a replacement cycle for the fume filter.
Finally they can display the total execution time and a percentage of the filter saturation on a simple display.

## High-level Block Diagram

![Flow Diagram](https://github.com/mic0331/smart_solder_fume_extractor/blob/main/doc/flow.png)

![Bloc Diagram](https://github.com/mic0331/smart_solder_fume_extractor/blob/main/doc/bloc.png)

## Main Components

### Microcontroller

STM32L476RGT6 using a [nucleo-L476RG](https://os.mbed.com/platforms/ST-Nucleo-L476RG/) development board.

### Particulate Matter Sensor

[Honeywell HPM Standard particulate matter sensor (32322550)](https://prod-edam.honeywell.com/content/dam/honeywell-edam/sps/siot/en-us/products/sensors/particulate-matter-sensors-hpm-series/documents/sps-siot-particulate-hpm-series-datasheet-32322550-ciid-165855.pdf) - UART

The Honeywell HPM Series Particulate Matter Sensor is a laser-based sensor which detects and counts particles using light scattering. The detection concentration range is
0 μg/m3 to 1,000 μg/m3. A laser light source illuminates a particle as it is pulled through the detection chamber. As particles pass through the laser beam, the light reflects 
off the particles and is recorded on the photo or light detector. The light is then analyzed and converted to an electrical signal to calculate particle concentration. The Honeywell 
particle sensor provides information on the particle concentration for given particle concentration range.

### Display

[LCD1602 LCD module](http://wiki.sunfounder.cc/index.php?title=LCD1602_Module) - I2C

### External EEPROM

[AT24C256](http://ww1.microchip.com/downloads/en/devicedoc/doc0670.pdf)- 256 kbit memory - I2C

### PWM Fan

Pulse-width modulated fan [Noctua NF-F12 PWM](https://www.amazon.fr/gp/product/B00650P2ZC/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1)

### Power System

TODO

For the development phase, two bench power supply will be used to power
the fan (12 VDC) and the sensor & display (5 VDC).
The MCU will be powed by the connected computer.