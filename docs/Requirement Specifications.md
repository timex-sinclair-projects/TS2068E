# TS2068E Hardware Design Requirements Specification


Revision History




Introduction
Purpose and Scope 
This document serves as a requirements specification for the design of the TS2068E computer. This document is intended to define the behavior of the TS2068E and does not, in general, dictate specific design methods or design choices. This document will contain both requirements and design goals. Requirements must be part of the design while goals may or may not appear in the design at the design engineers’ discretion.

Acronyms and Abbreviations 

Referenced Documents  


Hardware Description
Design Constraints

Packaging/Installation Design
Design Requirements
Z80 Processor
The processor shall be a Z80 processor with static design. The processor may be a cycle accurate and instruction accurate FPGA core.

If a processor core is used, it is permissible to extend the Z80 instruction set so long as the extensions do not affect the cycle and instruction accuracy of the core. Any instruction extensions shall be documented in the TS2068E manual.
Keyboard
The TS2068E shall have a USB keyboard interface.
The method used for the interface is at the engineer’s discretion.
TS2068 5V Expansion Bus
There shall be an expansion bus that is compatible with the original TS2068.
The expansion bus shall be compatible with 5V TTL logic.
TS2068 3V3 Expansion Bus
There shall be a 3.3V expansion connector that is compatible with the original TS268. The expansion be compatible with 3.3V TTL logic.
RAM Memory
There shall be at least 128k bytes of memory available for program memory space. The upper limit is at the engineer’s discretion.
Video Modes
All Standard TS2068 video modes shall be implemented.
ULA Plus Video
ULA Plus video shall be implemented in full.
Legacy TS2068 Software Compatibility
Legacy TS2068 software shall be supported by the hardware to the greatest extent possible.
Sound
There shall be a minimum of one AY8912 or equivalent IC and/or core in the design.
TS2068 Joysticks
There shall be provision for two TS2068 compatible joy sticks in the design
ZX Spectrum Joystick
There shall be provision for a Kempston compatible joystick interface in the design
Mass Storage
There shall be provision for mass storage in the design. Mass storage may be any combination of SD card or USB mass storage.
WiFi
There shall be provision for wifi connectivity
IF1 Type Support
There shall be provision in the hardware for Sinclair Interface 1 support. This support shall have a means to enable or disable support in the hardware.
This support shall intercept the RST0 and RST8 addresses and allow for automatic memory bank switching when an instruction if fetched from either of these addresses.
Serial Port
There shall be a RS232 serial port with hardware handshaking. The serial port shall have programmable baud rates that are compatible with industry standard rates.
Parallel Port
There shall be an 8 bit parallel port with 4 handshaking lines. The port shall allow connection to a printer using the Centronics protocol.
Memory Mapping
TS2068 Compatibility
The hardware shall allow mapping of memory that is compatible with the TS2068 (Home, Exrom, Dock). See the TS2068 technical manual for details.
Memory Chunk Size
All memory shall be divided into 8k chunks on 8k boundaries.
Memory Mapping, Bank/Chunk vs Physical Address
For Home, Exrom and Dock, any chunk in any given bank can be mapped to any physical 8k chunk in memory. This requirement explicitly allows a physical memory chunk to be mapped to more than one TS2068E bank. It also explicitly allows two or more chunks in a bank to reference the same physical memory chunk.
Memory Configurations
There shall be a minimum of four memory configurations. Each configuration shall contain the complete set of mapping registers for Home, Exrom and Dock. Selection of a configuration shall be done with a single memory write.

Design Goals
48K ZX Spectrum Expansion Bus
It is desired that a 48K ZX Spectrum compatible expansion bus be available.
Implementation of the bus is at the engineer’s discretion.
ZX Spectrum Software Support
Legacy ZX Spectrum software should be supported by the hardware to the greatest extent possible.
Secondary Joystick
A tertiary joystick is desired. This joystick will be interrogated at different, specified I/O or memory addresses.
Timex FDD Disk Commands
It is desired that the TC2068 floppy disk be supported
Sinclair ZXNET
It is desired that the hardware supports the ZXNET physical layer.
SPI Bus
It is desired that the hardware supports a SPI bus master with a minimum of two peripheral select lines. The hardware shall support all four (4) SPI modes.
I2C Bus
It is desired that the hardware supports two I2C busses. The busses shall allow clock rates of up to 1MHz.