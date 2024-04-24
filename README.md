# Arduino-nano-v3.1
Understanding the Arduino Nano v3.1 Configuration
Overview
The Arduino Nano v3.1 is a popular choice among beginners and hobbyists for its compact size and versatility. However, there can be confusion regarding its configuration, particularly regarding the clock frequency.

Internal Oscillator
Unlike some other Arduino boards, the Nano v3.1 doesn't have an external crystal oscillator. Instead, it utilizes its internal oscillator. By default, this oscillator runs at 8MHz.

Divider by 2
One crucial aspect to understand is that the Nano v3.1 has a divider by 2 enabled by default. This means that the internal oscillator's frequency is divided by 2, effectively resulting in an operating frequency of 4MHz.

Configuration Clarification
When configuring the Nano v3.1 in Arduino IDE or other development environments, it's important to note that although it's set to operate at 8MHz internally, the actual frequency is 4MHz due to the divider by 2.

Locating Configuration Files
To adjust the configuration, locate the Boards.txt file. On Windows 10 and 11, this file is typically found at:

``C:\Users\{YourUserName}\AppData\Local\Arduino15\packages\arduino\hardware\avr\1.8.6``

Replace ``{YourUserName}`` with your actual username on your computer.

Adding Configuration
To add the configuration for the Nano v3.1, open Boards.txt and add the relevant settings. Ensure that the configuration is placed at the top of the file for easy access.

Arduino Nano v3.1 Configuration

````
##############################################################
nano3_1.name=Arduino Nano v3.1

nano3_1.upload_port.0.board=nano3_1

nano3_1.upload.tool=avrdude
nano3_1.upload.tool.default=avrdude
nano3_1.upload.tool.network=arduino_ota
nano3_1.upload.protocol=arduino

nano3_1.bootloader.tool=avrdude
nano3_1.bootloader.tool.default=avrdude
nano3_1.bootloader.unlock_bits=0x3F
nano3_1.bootloader.lock_bits=0x0F

nano3_1.build.f_cpu=4000000L
nano3_1.build.board=AVR_NANO
nano3_1.build.core=arduino
nano3_1.build.variant=eightanaloginputs

## Arduino Nano v3.1 w/ ATmega328P
## --------------------------
nano3_1.menu.cpu.atmega328=ATmega328P

nano3_1.menu.cpu.atmega328.upload.maximum_size=30720
nano3_1.menu.cpu.atmega328.upload.maximum_data_size=2048
nano3_1.menu.cpu.atmega328.upload.speed=115200

nano3_1.menu.cpu.atmega328.bootloader.low_fuses=0xFF
nano3_1.menu.cpu.atmega328.bootloader.high_fuses=0xDA
nano3_1.menu.cpu.atmega328.bootloader.extended_fuses=0xFD
nano3_1.menu.cpu.atmega328.bootloader.file=optiboot/optiboot_atmega328.hex

nano3_1.menu.cpu.atmega328.build.mcu=atmega328p
````
Final Thoughts
Understanding the configuration details of the Arduino Nano v3.1, including its internal oscillator frequency and the effects of the divider by 2, can help troubleshoot issues and ensure proper operation of projects.

