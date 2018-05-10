# OneWire
OneWire library in C for atmega328P (arduino) compatible with 1Mhz-16Mhz clock

This library is based on library https://github.com/PaulStoffregen/OneWire v2.3. It implements the Maxim 1-Wire protocol (see https://www.maximintegrated.com/en.html)

I adapted this library to the AVR ATMEGA328 microcontroller (used in some arduino platforms).

Due to particular constraints of my project, I have experienced some issues with the OneWire libraries I found on internet.

1) The main issue I had concerns timing problems:
- wrong timing depending on compiler optimization
- wrong timing with low clock frequency (cpu clock of 1Mhz)
2) I want low power consumption for battery powered system.

Solutions I propose:
1) Time critical operations (write_bit/read_bit/parasitic_power) are written in assembly language to ensure perfect timing whatever the cpu clock frequency, compiler options... However, with the current implementation, cpu clock must be a multiple of 1Mhz, i.e. 1/2/3/.../16Mhz)
2) OneWire bus is based on pull-up resistors. To reduce power-consumption, an option can be enabled which consists in disabling pull-ups when master drives the line to ground.
3) The parasitic power option can be used to that only two lines are necessary to communicate with sensors.

Work in progress:
This library is in development and may not be reliable. But since most parts come from PaulStoffregen github so that everything should be working fine.

I work with free IDE Atmel Studio 7.0, avrgcc 5.4.0.
http://www.microchip.com/avr-support/atmel-studio-7
I'm using MAX31820 temperature sensors:
https://www.maximintegrated.com/en/products/sensors-and-sensor-interface/MAX31820.html


This package is the work of Emmanuel Ruffio. All is licensed under the GNU General Public License, version 3.

