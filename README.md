MSPDebug-CCS
========

MSPDebug is a free debugger for use with MSP430 MCUs. It supports
FET430UIF, eZ430, RF2500 and Olimex MSP430-JTAG-TINY programmers, as
well as many other compatible devices. It can be used as a proxy for
gdb or as an independent debugger with support for programming,
disassembly and reverse engineering.

This version of MSPDebug has been modified to interoperate better
with TI's Code Composer Studio. It supports a gdbserver style launch
option scheme, where the only argument is :port, port being the port
number to run a gdb server on. This permits it to be directly used as
a gdb server by CCS

Features
--------

  * Userspace only: no kernel modifications required.
  * Works with RF2500, eZ430, FET430UIF (V2 and V3), Launchpad, Chronos,
    GoodFET, Olimex MSP430-JTAG-TINY and MSP430-JTAG-ISO programmers.
    Also supports the TI flash bootloader.
  * Can act as a GDB remote stub (replacement for msp430-gdbproxy)
    and/or a GDB client.
  * Can single-step, program, run to breakpoint and inspect memory on
    supported devices.
  * Can be used to access the FET430UIF bootloader.
  * Supports Intel HEX, ELF32, BSD symbol table, COFF, TI Text and
    SREC file formats.
  * Can disassemble code in memory, including translating addresses to
    symbols.
  * Includes reverse-engineering features such as instruction search,
    call-graph analysis and symbol table editing.
  * Simulation mode allows execution of MSP430 code without hardware.
  * Cross-platform: compiles on Linux, *BSD, OS/X and Windows.

Compiling from source
---------------------

Ensure that you have the necessary packages to compile programs that use
libusb (on Debian or Ubuntu systems, you might need to do apt-get
install libusb-dev). After that, unpack and compile the source code
with:

    tar xvfz mspdebug-version.tar.gz
    cd mspdebug-version
    make

If you don't want GNU readline support, you can invoke make with:

    make WITHOUT_READLINE=1

After compiling, install the binary and manual page by running (as
root):

    make install

Type "mspdebug --help" for usage instructions.