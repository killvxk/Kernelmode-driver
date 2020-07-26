# What this is for:

This is a simple kernel driver for reading / writing process memory, it uses IOCTL communication, in case someone claims IOCTL communication is detected: byte patch a part of the ioctl function with a jmp I described that better in the source itself.

# Note:
This driver won't work on every Winver, until you update the memory addresses for it in the source code itself. Offsets that need to be changed are located in disk.sys, “ULONG64 hook Location = (ULONG64)diskSysBase + 0x32A2;” and “ ULONG64 returnPlaceOfIOCTL = (ULONG64)diskSysBase + 0x16AF; “. This is intended to be manually mapped.
