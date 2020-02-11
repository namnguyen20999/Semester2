### Firmware Creation
To power up the Raspberry, we need an SD card to load the OS inside it. We recommend to load the version name Raspbian Buster with desktop and recommended software because it has full functionality.

After you download the OS, leave it as zip file. Then download the software call Etcher, you can find it [here](https://www.balena.io/etcher/). This software is to flash the Image OS into the SD card. After you load the OS into SD card, insert it into the raspberry. Plug in the power supple

The one time set up is easy, so just follow the step on the OS.

After set everything up, the C file that use to read the temperature could be found [here](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Firmware/MCP9808.c). Use the command: gcc -g -o MCP9808 MCP9808.c to complie. Then the execution file will be MCP9808.

We also found a reference on how we could connect the Raspberry pi into the firebase to enable hardware integration and do a http request. Here is the [reference](https://www.hackster.io/varuldcube100/send-sensor-data-to-firebase-real-time-database-4d6b83).

Another flatform will be the Nucleo-F401RE which will be used to connect a temperature sensor but we are still trying to incorporate the temperature sensor into the Nucleo-F401RE. We will use STM32CUBEIDE to create and flash a http request program and enable the device to make an Http-Request into the firebase for the software and hardware integration. Here is the [main.c](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Firmware/main_http_request_f401re.c) for the sample Http-Request. We were able to connect it to a local wifi. Here is a capture confirming the connection happened.![Image](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Images/wifi%20connection%20capture.PNG?raw=true).

To perform this action, first we need to compile the http_request code and flash the binary file generated into the Nucleo-F401RE. Next press the reset button of the Nucleo-F401RE to run the fresh image. Then open a serial connection of the Nucleo-F401RE to set up the Wi-Fi peripherals. 
