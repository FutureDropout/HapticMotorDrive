# HapticMotorDrive

DRV2605 Haptic Motor Driver (0x5A)

Table of Contents

1. [Introduction](#introduction)

2. [Bills and Materials of Budget](#bills-and-materials-of-budget)

3. [Schedule](#schedule)

4. [DRV2605 Haptic Motor Driver Wiring](#drv2605-haptic-motor-driver-wiring)

4. [DRV2605 Haptic Motor Driver PCB Design Files](#drv2605-haptic-motor-driver-pcb-design-files)

5. [DRV2605 Haptic Motor Driver Assembly](#drv2605-haptic-motor-driver-assembly)

6. [DRV2605 Haptic Motor Driver PCB Soldering](#drv2605-haptic-motor-driver-soldering)

7. [DRV2605 Haptic Motor Driver Power Up](#drv2605-haptic-motor-driver-power-up)

8. [DRV2605 Haptic Motor Driver Testing](#drv2605-haptic-motor-driver-testing)

![ImageOfSensor](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/Sensor.JPG)

## Introduction

The DRV2605 Haptic Motor Driver is a sensor that has a vibrating and clicking feature. This haptic device can also be controlled by touching it by adding another touch sensor as input to the motor driver. The vibrating and clicking levels can be controlled by their intensity level. To receive an output of this sensor, another device must be connected to the output pins of the hardware. A vibration motor controller is used to buzz and click received by the haptic motor driver.

![Image of System Diagram](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/UMLDiagram.JPG)

## Bills and Materials of Budget

The <a href="https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/JordanPulidoBudget.JPG"> budget </a> was relatively cheap. A toolkit, a soldering kit, and a prototype lab are present before the project. The facilities at Humber College made the project drastically cheaper due to accessable sources.

![Image of Budget](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/JordanPulidoBudget.JPG)

## Schedule

## DRV2605 Haptic Motor Driver Wiring

The sensor would be placed on a breadboard. The pinouts would be connected to the raspberry pinouts through wiring. 

The following pinout is as follows:

| Device Pin                               | Pi Pinout  |
|------------------------------------------|------------|
| 1 (VIN)                                  | 1 (3.3V)   |
| 2 (GND)                                  | 9 (GND)    |
| 3 (SCL)                                  | 5 (GPI03)  |
| 4 (SDA)                                  | 3 (GPI02)  |

## DRV2605 Haptic Motor Driver PCB Design Files

The program <a href="http://fritzing.org/download/"> Fritzing </a> was used to make a diagram for wiring the raspberry pi and sensor.

![Image of Fritzing] ()

Fritzing was also used to do the PCB Milestone. The wires were placed so the upper levels wires won't overlap each other. The wires were placed so the lower level wires won't overlap each other. 

## DRV2605 Haptic Motor Driver Assembly



## DRV2605 Haptic Motor Driver PCB Soldering

A soldering toolkit is required to solder the PCB. The vias were soldered with soldering wire. A 40 pinout socket was used to solder on the lower level of the board for the raspberry pi pins. A 5 pinout socket was used to solder on the upper level board for the haptic motor drive pins. 

Top View

![Image of Top PCB](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/PCBSolderFront.jpg)

<br>

Bottom View

![Image of Bottom PCB](https://github.com/JordanPulido/HapticMotorDrive/blob/master/documentation/PCBSolderBack.jpg)

<br>

## DRV2605 Haptic Motor Driver Power up

## DRV2605 Haptic Motor Driver Testing
