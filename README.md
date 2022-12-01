# REV Color Sensor Raspberry Pi Pico

This uses a Serial connection to transmit data for 2 Rev Color Sensors to a roboRIO using a Pi Pico.

## Pi Pico Setup

You can follow the raspberry pi instructions to build the executable in the pico folder. Their instructions are complicated for windows, so I have also provided a prebuilt uf2 file to directly upload to the device. To deploy this file this, hold down the button on your devide, and connect to your computer. This will open as a drive. Copy the picocolorsensor.uf2 file in the `pico` folder to the drive. It will automatically reboot and start running the code with no configuration required.

## Hardware connections

By default, the code will connect to 2 color sensors. 

Please solder all the necessary components onto the PCB, files are provided in the `Pico Color Sensor PCB` folder to print/order your own PCB as well as the Bill of Materials(BOM) needed for the PCB.

You may solder both the DuPont and/or the JST connector but you may only use one on both sides.

## WPILib Setup

Copy the files corresponding to the language you use in the `wpilib` folder into your project. Instantiate a `PicoColorSensor` (java) or `pico::ColorSensor` (C++) object. You can only create 1 instance of this object. You can then use the functions to grab each color sensors value, and if its connected.
