# REV Color Sensor Raspberry Pi Pico

This uses a Serial connection to transmit data for 2 Rev Color Sensors to a roboRIO using a Pi Pico.

## Pi Pico Setup

You can follow the raspberry pi instructions to build the executable in the pico folder. Their instructions are complicated for windows, so I have also provided a prebuilt uf2 file to directly upload to the device. To deploy this file this, hold down the button on your devide, and connect to your computer. This will open as a drive. Copy the picocolorsensor.uf2 file in the `pico` folder to the drive. It will automatically reboot and start running the code with no configuration required.

## Hardware connections

By default, the code will connect to 2 color sensors. 

Please solder all the necessary components onto the PCB, files are provided in the `Pico Color Sensor PCB` folder to print/order your own PCB as well as the Bill of Materials(BOM) needed for the PCB.

You may solder both the DuPont and/or the JST connector but you may only use one on both sides.

V2

![image](https://user-images.githubusercontent.com/43244309/232900334-44a62617-8657-4d1d-9676-eb34dcb25fee.png)

Differences between V1 and V2:

* Replaced the SMDs with THTs components so teams don’t need to worry about small pieces and allows easier soldering with THTs
* Made the DuPont headers at a right angle to minimize the usage of the vertical space
* Both the Dupont and JST connector face the side
* FIXED: The JST connector on the V1 had the SDA and SCL channels in the wrong pins, V2 has fixed that. This allows you to use a regular 4-pin JST PH cable from the color sensor to the board. NOTE: When plugging the JST connector into the board, the connector must be upside down then how you plug into the color sensor.

V2.1

![image](https://user-images.githubusercontent.com/43244309/232899958-a795e368-84da-44f7-bdfd-289be4d453f4.png)

V2.5

![image](https://user-images.githubusercontent.com/43244309/232900142-c6cc3330-3f3e-4746-af63-4428063e00ea.png)

Differences between V2 and V2.1/V2.5

* V2.1 and V2.5 now have 4 layers of traces instead of 2

Differences between V2.1 and V2.5

* V2.5 now has a male MXP port to allow you to use a NavX.
* V2.5 also has extra mounting holes for you to be able to securely mount the NavX
* NOTE: Due to the rule R713 in the 2022 Game Manual, you are not allowed to use any of the pins available on the NavX to control any actuators


## WPILib Setup

Copy the files corresponding to the language you use in the `wpilib` folder into your project. Instantiate a `PicoColorSensor` (java) or `pico::ColorSensor` (C++) object. You can only create 1 instance of this object. You can then use the functions to grab each color sensors value, and if its connected.
