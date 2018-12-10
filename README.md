# HapticMotorDrive

DRV2605L Haptic Motor Driver (0x5A)

Table of Contents

1. [Introduction](#introduction)

2. [Bills and Materials of Budget](#bills-and-materials-of-budget)

3. [Schedule](#schedule)

4. [DRV2605L Haptic Motor Driver Wiring](#drv2605l-haptic-motor-driver-wiring)

5. [DRV2605L Haptic Motor Driver PCB Design Files](#drv2605l-haptic-motor-driver-pcb-design-files)

6. [DRV2605L Haptic Motor Driver Assembly](#drv2605l-haptic-motor-driver-assembly)

7. [DRV2605L Haptic Motor Driver PCB Soldering](#drv2605l-haptic-motor-driver-pcb-soldering)

8. [DRV2605L Haptic Motor Driver Power Up](#drv2605l-haptic-motor-driver-power-up)

9. [DRV2605L Haptic Motor Driver Testing](#drv2605l-haptic-motor-driver-testing)

![ImageOfSensor](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/Sensor.JPG)

## Introduction

The DRV2605 Haptic Motor Driver is a sensor that has a vibrating and clicking feature. This haptic device can also be controlled by touching it by adding another touch sensor as input to the motor driver. The vibrating and clicking levels can be controlled by their intensity level. To receive an output of this sensor, another device must be connected to the output pins of the hardware. A vibration motor controller is used to buzz and click received by the haptic motor driver.

![Image of System Diagram](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/UMLDiagram.JPG)

## Bills and Materials of Budget

The <a href="https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/Budget.JPG"> budget </a> was relatively cheap. A toolkit, a soldering kit, and a prototype lab are present before the project. The facilities at Humber College made the project drastically cheaper due to accessable sources.

![Image of Budget](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/Budget.JPG)

## Schedule

The schedule should roughly take 

## DRV2605L Haptic Motor Driver Wiring

The sensor would be placed on a breadboard. The pinouts would be connected to the raspberry pinouts through wiring. 

The following pinout is as follows:

| Device Pin                               | Pi Pinout  |
|------------------------------------------|------------|
| 1 (VIN)                                  | 1 (3.3V)   |
| 2 (GND)                                  | 9 (GND)    |
| 3 (SCL)                                  | 5 (GPI03)  |
| 4 (SDA)                                  | 3 (GPI02)  |

![Image of Raspberry Pi Pinouts](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/raspberrypiPinouts.jpg)

HERE YOU CAN CLICK A <a href="https://radiojove.gsfc.nasa.gov/telescope/soldering.htm"> TUTORIAL </a> ON HOW TO SOLDER SAFELY AND EFFICIENTLY.

A 5 pinout socket was placed on the bottom layer of the sensor. Both sides of the pin sockets were soldered. The vibrating controller motor was soldered with the blue wire on the negative socket and the red wire on the positive socket.

![Image of Soldered Sensor](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/Sensor%20soldered.jpg)

## DRV2605L Haptic Motor Driver PCB Design Files

The program <a href="http://fritzing.org/download/"> Fritzing </a> was used to make a diagram for wiring the raspberry pi and sensor.

![Image of Fritzing](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/fritzingWiring.JPG)

Fritzing was also used to do the PCB Milestone. The wires were placed so the upper levels wires won't overlap each other. The wires were placed so the lower level wires won't overlap each other.

![Image of PCB Milestone](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/PCBFritzing.JPG)

## DRV2605L Haptic Motor Driver Assembly

A SD Card (SD Card is provided from the <a href="https://www.amazon.ca/CanaKit-Raspberry-Starter-Premium-Black/dp/B07BCC8PK7/ref=sr_1_1_sspa?s=pc&ie=UTF8&qid=1544123414&sr=1-1-spons&keywords=raspberry+pi+3+b%2B&psc=1&smid=A34IVHW5OUAV7P"> raspberry pi 3 kit</a>) formatter was installed.

https://www.sdcard.org/downloads/formatter_4/

NOOBS was installed to give the operating system (os) for the SD card.

https://www.raspberrypi.org/downloads/noobs/

The setup for the raspberry pi was done with reference by <a href="https://www.lynda.com/Raspberry-Pi-tutorials/Raspberry-Pi-Essential-Training/667376-2.html">Lynda</a>.

## DRV2605L Haptic Motor Driver PCB Soldering

A soldering toolkit is required to solder the PCB. The vias were soldered with soldering wire. A 40 pinout socket was used to solder on the lower level of the board for the raspberry pi pins. A 5 pinout socket was used to solder on the upper level board for the haptic motor drive pins.

Top View

![Image of Top PCB](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/PCBSolderFront.jpg)

<br>

Bottom View

![Image of Bottom PCB](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/PCBSolderBack.jpg)

<br>

## DRV2605L Haptic Motor Driver Power up

To enable VNC, 

Once VNC is enabled, the following code was typed to identify the address of the given sensor.

```
sudo i2cdetect -y 1
```

![Image of Address](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/address.jpg)

## DRV2605L Haptic Motor Driver Testing

For the Driver to begin its testing, A python and circuitpython installation has been made into the raspberry pi. <a href="https://www.adafruit.com/"> Adafruit </a> has been used as reference to install the libraries.

The link to completely install python can be found by clicking <a href="https://learn.adafruit.com/adafruit-drv2605-haptic-controller-breakout/python-circuitpython"> HERE </a>.

Type in this code to build the circuitpython tools package

```
python3 -m venv .env
source .env/bin/activate
pip install circuitpython-build-tools
```

Once installed, test run if you are connected to the tools package

```
source .env/bin/activate
```

Run the build

```
circuitpython-build-bundles --filename_prefix adafruit-circuitpython-drv2605 --library_location 
```

Install CircuitPython

```
sudo pip3 install adafruit-circuitpython-drv2605
```

Once installed, import the modules and identify the i2c connection with the motor.

```
import board
import busio
import adafruit_drv2605
i2c = busio.I2C(board.SCL, board.SDA)
drv = adafruit_drv2605.DRV2605(i2c)
```

Here is an example of code running the Haptic Motor Drive by Adafruit.

```
# Simple demo of the DRV2605 haptic feedback motor driver.
# Will play all 117 effects in order for about a half second each.
# Author: Tony DiCola
import time
 
import board
import busio
 
import adafruit_drv2605
 
 
# Initialize I2C bus and DRV2605 module.
i2c = busio.I2C(board.SCL, board.SDA)
drv = adafruit_drv2605.DRV2605(i2c)
 
# Main loop runs forever trying each effect (1-117).
# See table 11.2 in the datasheet for a list of all the effect names and IDs.
#   http://www.ti.com/lit/ds/symlink/drv2605.pdf
effect_id = 1
while True:
    print('Playing effect #{0}'.format(effect_id))
    drv.sequence[0] = adafruit_drv2605.Effect(effect_id)  # Set the effect on slot 0.
    # You can assign effects to up to 7 different slots to combine
    # them in interesting ways. Index the sequence property with a
    # slot number 0 to 6.
    # Optionally, you can assign a pause to a slot. E.g.
    # drv.sequence[1] = adafruit_drv2605.Pause(0.5)  # Pause for half a second
    drv.play()  # Play the effect.
    time.sleep(0.5)
    # Increment effect ID and wrap back around to 1.
    effect_id += 1
    if effect_id > 117:
        effect_id = 1
```

Set a waveform for the motor's ID corresponding to its physical effects. Here is an example.

```
drv.set_waveform(84)         # Effect 84 in slot 0
drv.set_waveform(1, slot=1)  # Effect 1 in slot 1
drv.set_waveform(0, slot=2)  # End effects after slot 1 (set slot 2 to 0)
drv.play()
```






