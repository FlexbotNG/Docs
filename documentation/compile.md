---
layout: default
title: Compile the FlexbotNG from source
---

# Install FlexbotNG on your flight-controller

If you just want to install FlexbotNG on your flight-controller we recommend our [FlashTool](flashtool), which is supported on Windows and MacOSX.

If you want to compile it yourself or have special configuration needs that are not possible with the FlashTool, follow this page.

# How to compile FlexbotNG from source

## Prerequisites

* ArduPilot-Arduino 1.0.3

  You need a special version of the Arduino software to compile the source.
  
  * [ArduPilot-Arduino-1.0.3 for Windows with GCC 4.8.2](http://firmware.diydrones.com/Tools/Arduino/ArduPilot-Arduino-1.0.3-gcc-4.8.2-windows.zip) (~190 MB)
  * [ArduPilot-Arduino-1.0.3 for MacOSX](http://ardupilot.com/downloads/?did=44) (~80 MB)

* The latest sourcecode

  * [FlexbotNG - APM:Copter](https://github.com/FlexbotNG/ardupilot-mpng)
  * [FlexbotNG - APM:Plane 2.76](https://github.com/smurfy/ardupilot-mpng)

  If you know your way around GIT you also can clone the respective repository from github.com
  
## Prepare your Environment

* Extract ArduPilot-Arduino 1.0.3, for example to ```c:\quadcopter```
  
  Make sure that the full pathname is not longer than ```255``` chars, or you could encounter compile problems.

  You now should have a directory called ```ArduPilot-Arduino-1.0.3-windows``` (Windows) or an ```Arduino``` application (MacOSX) in the ```c:\quadcopter``` directory.
* Extract the downloaded source code, for example to ```c:\quadcopter```

  You now should have a new directory in the ```c:\quadcopter``` directory called like the zip file.
  In our example we use the name ```ardupilot-mpng``` for this directory.

* ***Important*** Replace the shipped ```pde.jar``` from the source directory to the ardupilot-arduino software.

  Windows:

  Locate the ```pde.jar``` in your sources root directory for example ```c:\quadcopter\ardupilot-mpng\pde.jar```,
  copy and replace the file with the file in ```c:\quadcopter\ArduPilot-Arduino-1.0.3-windows\lib```

  MacOSX:

  Locate the ```pde.jar``` in your sources root directory for example ```~username/quadcopter/ardupilot-mpng/pde.jar```,
  copy and replace the file with the file in ```~username/quadcopter/Arduino.app/Contents/Resources/Java```
* Start ArduPilot-Arduino

* Change the target-platform to FlexbotNG

  ![Arduino Platform](../images/compile_arduino_platform.jpg)
* Open preferences and set the sketch folder to the source code directory, for example ```c:\quadcopter\ardupilot-mpng```

  ![Arduino preferences](../images/compile_arduino_preferences1.jpg)
  ![Arduino preferences](../images/compile_arduino_preferences2.jpg)

  You also should uncheck the "Update sketch files to new extension on save" checkbox.

* Connect your Flight Controller to your Computer and set the Serial Port in the Arduino IDE

  ![Arduino preferences](../images/compile_arduino_set_serialport.jpg)

* ***Important*** Restart the Arduino IDE

## Compiling

Now open your desired APM Autopilot Platform (ArduCopter, ArduPlane...) via ```File > Sketchbook```.

To compile the source code, pressing either the first icon in the toolbar or press ```ctrl+R```.

If your source compiles without a problem you are ready to begin to configure your UAV.
