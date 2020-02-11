### Firmware Creation
Dear Mr. Medri,
Here is the report regarding on how we will be making our images/firmwares. This is summarazion on how we did it on the previous semester to be able read from our sensors and display it using either a serial connection or a console of an IDE.
First we used a Raspberry pi for our temperature sensor(MCP9808). To do this image, here's the steps.

To power up the Raspberry, we need an SD card to load the OS inside it. We recommend to load the version name Raspbian Buster with desktop and recommended software because it has full functionality.

After you download the OS, leave it as zip file. Then download the software call Etcher, you can find it [here](https://www.balena.io/etcher/). This software is to flash the Image OS into the SD card. After you load the OS into the SD card, insert it into the raspberry. Plug in the power supply

The one time set up is easy, so just follow the step on the OS.

After set everything up, the C file that use to read the temperature could be found [here](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Firmware/MCP9808.c). Use the command: gcc -g -o MCP9808 MCP9808.c to complie. Then the execution file will be MCP9808.

We also found a reference on how we could connect the Raspberry pi into the firebase to enable hardware integration and do a http request. Here is the [reference](https://www.hackster.io/varuldcube100/send-sensor-data-to-firebase-real-time-database-4d6b83).

Another flatform we will be the Nucleo-F401RE which will be used to connect a temperature sensor but we are still trying to incorporate the temperature sensor into the Nucleo-F401RE. The Nucleo-F401RE will also have a Wi-Fi expansion module for IoT connectivity that we will be using to connect to the Firebase. We will use STM32CUBEIDE to create and flash a http request program and enable the device to make an Http-Request into the Firebase for the software and hardware integration. Here is the [main.c](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Firmware/main_http_request_f401re.c) for the sample Http-Request that we will be updating to support our hardware/software integration. We were able to connect it to a local wifi/hotspot. Here is a capture confirming the connection was successful.![Image](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Images/wifi%20connection%20capture.PNG?raw=true).

To perform this action, first we need to compile the http_request code and flash the binary file generated into the Nucleo-F401RE. Next press the reset button of the Nucleo-F401RE to run the fresh image. Then open a serial connection of the Nucleo-F401RE to set up the Wi-Fi peripherals. To read the temperature from the RTDPT100 attached to the Nucleo-F401RE we tried a assembly code written by Adrian on previous semester that converts the voltage readings from the RTDPT100 into a temperature. Here is the sample [code](https://github.com/namnguyen20999/SmartHome-Entry-CapstoneProject/blob/master/Firmware/RTDPT100READ.ino) for it. For this particular code, we use the Arduino bluepill to program and read temperature from the RTDPT100 and display the readings using a serial connection.




