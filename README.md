Features
======

A USB to Serial Converter firmware using FTDI FT232BM protocol. 

It also can automatically detect ESP32 bootloader flow control message, and it will never hurts normal mode (If the host program sets RTS and DTR both high or low, the firmware will force those pins all high).

Issues
--------------

Baudrate range: 1200bps - 1.5Mbps

USB endpoints are not configured as ping-pong mode, it makes it even slower. The real performance of this dongle is about 978Kbps, measured by esptool.

This usb to serial converter does not contains any hardware flow control feature and it can only works with 8N1 line coding. I'm working on parity support, but I'm lack of time.

Warning: High baudrate is not accurate at all, 115200 is the last traditional baudrate that it supports. For higher baudrate, please use 250Kbps, 500Kbps, 750Kbps, 1.5Mbps.

Optimizing this code (by rewritten it in assembly) is just like real hell working.


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


