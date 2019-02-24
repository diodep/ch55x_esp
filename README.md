Features
======

A USB to Serial Converter firmware using FTDI protocol. 

It also can automatically detect ESP32 bootloader message, force it enter ISP mode without help from FLOW CONTROL PINs (DTR/RTS).

Issues
--------------

Baudrate range: 5859bps - 750Kbps.

Warning: Due to slow 8051-based CPU and SDCC's interrupt handler code generation policy, it can't receive properly at 1.5Mbps.

USB endpoints are not configured as ping-pong mode, it makes it even more slow. The real performance of this dongle is about 657Kbps, measured by esptool.

Warning: High baudrate is not accurate at all, 115200 is the last traditional baudrate that it supports. For higher baudrate, please use 250Kbps, 500Kbps, 750Kbps.

So, my advice is... Don't use this puppy to make USB to Serial Bridge? CH330, CH340, HT42B534 and GD32F150/STM32F103're better choice than CH55x series MCU.


Boards
--------------

M5Stack II.

Build
--------------

It requires make, sdcc and binutils.

If you got all of them, enter the src directory, and type "make" to generate binary file.

Programming
--------------

By WinchipHead's official WCHISPTOOL or LibreCH551 from rgwan.

License
--------------

MIT

Authors
--------------

Kongou Hikari <kongouhikari@qq.com>

