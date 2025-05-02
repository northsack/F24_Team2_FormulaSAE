# How to use the FSAE Electric Powertrain
##### 4/25/2025

## Overview
This document outlines how to operate/configure the powertrain for the Formula SAE Electric vehicle.  Caution must be taken when turning on power supplies to the motor controller.  If the main operating power supplies are turned on when the precharge circuit is still active, the precharge circuit can be damaged, and the motor controller will be bricked.

## Setup
Our project uses a total of six RIGOL DP832 power supplies.  For this project, we divided these power supplies into banks.  A bank consists of two of these power supplies connected in series such that the bank provides 104 V DC.  Two banks are connected in parallel to the main power terminals of the motor controller to emulate the battery. Additionally, one bank is used to power the keyswitch.  

![image](https://github.com/northsack/F24_Team2_FormulaSAE/blob/main/Documentation/Images/P1-Overview.JPG)

In this image, the left four power supplies are connected to the battery connections on the motor controller.  The two power supplies on the right are connected to the SW1 on the switch bank which is connected to the keyswitch C90 pins on the motor controller.

### Power Supply Purpose: 
##### Keyswitch (1 bank on right)
The keyswitch power supplies are needed because you need the same battery voltage applied at the keyswitch C90 pins to turn on the motor controller.  You have to turn on these power supplies and flip the keyswitch **before** you turn on the main power supplies (or connect the battery).  Something that I discovered after a lot of research is that the motor controller precharges itself through the keyswitch and the keyswitch power supplies.  This is confusing, but it's the way the controller was designed.

##### Main Power (2 banks on left)
These power supplies should only be turned on once the motor controller is precharged.

## Use

A mulitmeter should be connected to measure the voltage across the motor controller's main terminals connected to the main power supplies.  This measures the state of the precharging.

To run the motor, the following procedure should be followed:
1) Turn on the keyswitch power supplies
2) Disconnect the leads connecting the main power supplies to the main terminals on the motor controller.  Make sure these leads are not touching metal as there will be a charge on them temporarily while you are starting the motor controller.
3) Turn on all of the main power supplies (Leads should be disconnected from the motor controller!)
4) Turn on the key switch.
5) Watch the multimeter measuring the voltage across the motor controller's main terminals.  Once the multimeter reads 50 V **AND** the voltage starts decreasing then proceed to the next step. This step should take about 4 seconds.

**IMPORTANT** If you do not wait for the voltage to start dropping, you will connect the power supplies while the precharge system is still engaged.  This WILL destroy the motor controller!  Wait until the voltage drops to ensure the precharge circuit is disengaged.
6) Connect the leads connected to the motor controller main terminals to the main power supplies.
7) You are done!

## Summary
The reason you can't leave the main power supplies connected to the motor controller is because these power supplies have internal bleeder resistors.  If you leave them connected while the motor controller is precharging, these bleeder resistors will discharge your precharge circuit.  This is why you must have the power supplies on when you connect them to the motor controller.
