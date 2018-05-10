# OneWire
OneWire library in C for atmega328P (arduino) compatible with 1Mhz-16Mhz clock

This library is based on library https://github.com/PaulStoffregen/OneWire v2.3. It implements the Maxim 1-Wire protocol (see https://www.maximintegrated.com/en.html)

I adapted this library to the AVR ATMEGA328 microcontroller (used in some arduino platforms).

Due to particular constraints of my project, I have experienced some issues with the OneWire library implementation I found on internet.

1) The main issue I had concerns timing problems:
- wrong timing depending on compiler optimization
- wrong timing with low clock frequency (internal RC oscillator 1Mhz)

2) I want to reduce power consumption of the library for battery powered system.

This package is the work of Emmanuel Ruffio. All is licensed under the GNU General Public License, version 3.

