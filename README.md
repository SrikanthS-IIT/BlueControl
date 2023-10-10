# BlueControl v1.0
[EE536: Internet of Things] BlueControl : Instrument Automation with SCPI over Bluetooth

## Background

![image](https://github.com/SKundawal/BlueControl/assets/61798659/f9c1187a-2393-46a0-9c0e-e9040619d1ac)

Remote control of instruments is an important tool to have in labs. This is particularly handy if a well-established protocol of measurement has to be repeated over several parameters. SCPI commands are the way to go when it comes to remote control, with packages like MATLAB and Python offering support via NI-VISA, or pyserial. 

Those who do automate are also aware of the mess of wires that comes with it. A certain level of respite is offered by the use of LAN, decoupling the base station from the connected devices. However it is not a given that all labs will have this facility. 

Here, we provide an alternative to the existing methodologies of remote control, by offering Bluetooth-based connectivity using the Raspberry Pi. Here, a Raspberry Pi is used as a base station that communicates with a remote Raspberry Pi via the Bluetooth protocol. SCPI commands are sent over the remote connection. The Bluetooth protocol does away the need of a WiFI/LAN connection, and allows the control of multiple instruments within a small lab with ease. No more clutter of USB, LAN or GPIB cables :)

In principle, one can envision a series of RPI stations connected to multiple devices - each uniquely addressable - or (a more ambitious goal) individual RPI Zeros plugged directly onto the instruments. The vision is to arrive at a Bluecontrol Dongle for an instrument. 

This is work in progress - I hope that making these codes available as open-source will help development of this tool. Do let us know if you found the tool useful, or if you think we can make some changes. 

This tool was developed as part of the IIT Mandi EE535P Internet of Things course (2023 Spring Summer semester) by MTech Computer Science Students ***Mahima Gupta*** and ***Sandeep Nathuram Kundalwal***, both of whom contributed to the work equally. We also thank the course instructor ***Dr. Siddhartha Sarma*** of the School of Computing and Electrical Engineering, IIT Mandi for his insightful comments. 

## Package dependencies
The following Python modules are required:
1. pyserial or pyusb
2. pyvisa (for sending SCPI commands to instruments)
3. pybluez (bluetooth library)
4. zeroconf (instrument discovery and service registration) - Without this, the code generates a warning.

## Functionality 
At present, the code has been tested for the following instruments:
1. DSOX1102A KeySight Technologies (Digital Storage Oscilloscope)
2. AFG1062 Tektronix (Arbitrary Function Generator) 

## Scope
We would like to add the following functionalities in the next version. 
1. **Adding more functionality** - Few scpi commands are not working (trying to figure out why...)
2. **Direct store to RPi** - Store output from query commands in a file.
3. **Scripting** - SCPI commands can be given using a file with input values.
4. **GUI Based control** - Make a proper desktop application for the same.
