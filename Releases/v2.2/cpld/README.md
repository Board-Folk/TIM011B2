This directory contains the project and .pof file for programming U50 - EPM7128 which replaces the discrete circuitry which generates the video signal in TIM011B.

If you want to recompile the code, you need Altera Quartus II v13.0.1.232 Web Edition which is available on Altera web site.

To program the CPLD, you can use the Altera Quartus II 13.1 programmer and a Altera Blaster USB programmer which is available for cheap on AliExpress.

The CPLD is 100% compatible with the TTL implementation, but has extended features - horizontal scroll register, sync signal inversion and 256x256 16 color mode.

The original (vertical) scroll register is still at I/O address 0xD0. The horizontal scoll (which, by design, scrolls by 4 pixels in 512x256 and 2 pixels in 256x256 mode) is at 0xD4 (and has only 128 possible values). To switch to 16 colors, write a 1 to I/O address 0xD8, and to revert to 512x256 write a 0 in the same register.

The color output (when active) is only available on the DB9 RGBI connector, which is wired to IBM CGA standard. The composite output is always in B/W and in 512x256 pixels.

For some monitors (if connected via RGBI connector) you have to invert the sync signals (they require positive sync). This is accomplished by a jumper that is provided on board.

The pinout of the CPLD is not optimal, it was selected for a prototype board attached to TIM011B v1.3 board. In the final revision, the pinout will be revised for optimal board routing.