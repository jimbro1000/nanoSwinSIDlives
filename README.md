# NanoSwinSID #

This project contains schematics and pcb design for
the simple "nano SwinSID b", based on Swinkels original
design. The hex code for programming the AtMega88 
core is not included. You can find that at 
http://www.tolaemon.com/nss/ .

The schematics have been transcribed from those
presented on that same page. The PCB design,
while close to the original, is unique to this
repository.

The schematics and PCB design have been created
using KiCad 7.

## Construction ##

The repository includes gerber files for
submitting to the likes of JLCPCB or PCBway,
any of which can create small batches of the
board at low cost.

### B.o.M. ###

An interactive BOM is available within this 
repository in the "/bom" folder. This includes
a positioning reference to make the placing of
components much easier!

| Item | Qty | Reference(s) | Value        | Datasheet |
|------|-----|--------------|--------------|-----------|
| 1    | 1   | C1           | 0.1uF        | ~         |
| 2    | 1   | D1           | LED          | ~         |
| 3    | 1   | host_lower1  | 01-14        | ~         |
| 4    | 1   | host_upper1  | 15-28        | ~         |
| 5    | 2   | R1, R3       | 1K           | ~         |
| 6    | 1   | R2           | 240K         | ~         |
| 7    | 1   | R4           | 2K2          | ~         |
| 8    | 1   | R5           | 4K7          | ~         |
| 9    | 1   | R6           | 330          | ~         |
| 10   | 1   | U1           | ATmega88PA-A | http://ww1.microchip.com/downloads/en/DeviceDoc/ATmega48PA_88PA_168PA-Data-Sheet-40002011A.pdf |
| 11   | 1   | U3           | Program      | ~         |
| 12   | 1   | U5           | ASDMB-32MHz  | ~         |

Note. R6 and D1 are optional and only needed
to provide the "underglow" when powered up

## Assembly ##

All of the components, with the exception of
the headers are surface mount. How you go about
soldering these components to the board is up 
your preference.

It is substantially easier to mount the components 
and then mount the header pins.

A solder paste stencil for such a small board
is a minor addition to the price when
ordering if you prefer using paste and makes
assembly pretty simple.

Pay attention to the reference pins for the
oscillator and the AtMega88. Pin 1 of the
AtMega88 is to the top right (marked with a
single dot). The oscillator pin 1 is to the
bottom left (again marked with a single dot).

For the headers it is important to use round
pins (aka turned pins) unless you are soldering
the swinSID directly to the board (which would
be unlikely given the original SID chips are 
all socketed). Using the regular square pins
will damage the socket by spreading the individual
pin sockets permanently and making a switch 
back to an original SID much more difficult.

The board has a pre-bridged jumper position to
select either a 6581 or 8580. By default it is
set to 6581. If the board is being prepared for
an 8580 then the bridge must be cut between
pin 1 and pin 2; and a solder bridge added
from pin 2 to pin 3.

## Programming ##

In order to program the AtMega88 you need a
harness to convert the regular connection to
the 1.27mm pitch header row on the board.

The page at http://www.tolaemon.com/nss/ has
some reasonable step-by-step instructions on
how to perform the programming.

There are two versions of the firmware linked
on the same page. The original provides a 
ping/beep when powered up. An alternative 
silent version of the firmware is also 
provided for those that want a degree more
realism to the emulation.

If you want the raw source code for the original
firmware you can find it at 
https://github.com/dmantione/swinsid

## Thank you ##

Thanks to Swinkels, x1541 and Tolaemon for providing
the source material that made this possible.

Swinkels' site seems to have been taken down but
a copy is held on the web archive:
https://web.archive.org/web/20220517042218/http://www.swinkels.tvtom.pl/swinsid/

Also thanks to dmantione for rescuing the source
code.
