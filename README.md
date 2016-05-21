# CasioGraphicsCalculator_Software
This is all of the software I've written for the Casio CFX-series graphics calculator. (will be updated as I write more code)

**Periodic table**

This is a program I wrote back in 2011 which lets you browse the periodic table, in graphical form, on the Casio graphics calculator (tested on fx9750G Plus.)  Slow but usable, and uses up all but 1706 bytes (out of 28628 bytes) of memory.

**TextAndDataStorage.cat**

This is a program which lets you store text data on a Casio graphics calculator. It exploits the fact that the calculator can store 15 digit-precision numbers, provided they're calculated and not explicitly entered (e.g. 1.23456789012345 gets truncated to 1.234567890, 2^49 - 1 makes a big long 15-digit number.)  This method allows you to store 56 bits of information in a 10-byte variable, which doesn't sound like much but it allows you to store 8 7-bit characters per cell in a matrix, which is not too bad when all things are considered.

The method I have used is a bit of a hack - text/string storage is not natively supported (it is a graphics calculator after all) so I've had to do some pretty ugly stuff to get it to work.  It's slow and as a result quite painful to use, but to my knowledge it's the most efficient way of storing text data to be transmitted (this isn't a native feature and is far from the calculator's intended functionality!)  This should work much faster on the FX9750GII calculator, and it should in theory be compatible with both the fx9750G Plus and fx9750GII (only tested on the G Plus.)  As text/data is stored in a matrix, it can then be sent via the serial port and the Send(Mat n) command to some external device, such as an Arduino Nano and WiFi module/radio.  It will be interesting to see what previously impossible applications for the graphics calculator this opens up.

To run, you'll need at least 12500 bytes' free memory.
