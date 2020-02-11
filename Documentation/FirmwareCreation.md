### Firmware Creation
To power up the Raspberry, we need an SD card to load the OS inside it. The link to raspbian is here. We recommend to load the virsion name Raspbian Buster with desktop and recommended software because it has full functionality.

After you download the OS, leave it as zip file. Then download the software call Etcher, you can find it here. This software is to flash the Image OS into the SD card. After you load the OS into SD card, insert it into the raspberry. Plug in the power supple

The one time set up is easy, so just follow the step on the OS.

After set everything up, the C file that use to read the temperature could be found here Use the command: gcc -g -o MCP9808 MCP9808.c to complie. Then the execution file will be MCP9808.
