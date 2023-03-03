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

| Item | Qty | Reference(s) | Value | LibPart | Footprint | Datasheet | DNP |
|------|-----|--------------|-------|---------|----------|-----------|-----|
| 1 | 1 | C1 | C_Small | Device:C_Small | Capacitor_SMD:C_0805_2012Metric | ~ | | |
| 2 | 1 | D1 | LED | Device:LED_Small | Diode_SMD:D_0805_2012Metric | ~ |  | |
| 3 | 1 | host_lower1 | 01-14 | Connector:Conn_01x14_Pin | Connector_PinHeader_2.54mm:PinHeader_1x14_P2.54mm_Vertical | ~ |  | |
| 4 | 1 | host_upper1 | 15-28 | Connector:Conn_01x14_Pin | Connector_PinHeader_2.54mm:PinHeader_1x14_P2.54mm_Vertical | ~ |  | |
| 5 | 1 | J1 | 6581 | Connector:Conn_01x02_Pin | Connector_PinHeader_2.00mm:PinHeader_1x02_P2.00mm_Vertical | ~ |  | |
| 6 | 1 | J2 | ~ | Connector:Conn_01x02_Pin | Connector_PinHeader_2.00mm:PinHeader_1x02_P2.00mm_Vertical | ~ |  | |
| 7 | 2 | R1, R3 | 1K | Device:R_Small | Resistor_SMD:R_0805_2012Metric | ~ |  | |
| 8 | 1 | R2 | 240K | Device:R_Small | Resistor_SMD:R_0805_2012Metric | ~ |  | |
| 9 | 1 | R4 | 2K2 | Device:R_Small | Resistor_SMD:R_0805_2012Metric | ~ |  | |
| 10 | 1 | R5 | 4K7 | Device:R_Small | Resistor_SMD:R_0805_2012Metric | ~ |  | |
| 11 | 1 | R6 | 330 | Device:R_Small | Resistor_SMD:R_0805_2012Metric | ~ |  | |
| 12 | 1 | U1 | ATmega88PA-A | MCU_Microchip_ATmega:ATmega88PA-A | Package_QFP:TQFP-32_7x7mm_P0.8mm | http://ww1.microchip.com/downloads/en/DeviceDoc/ATmega48PA_88PA_168PA-Data-Sheet-40002011A.pdf |  | |
| 13 | 1 | U3 | Program | Connector:Conn_01x06_Pin | Connector_PinHeader_1.27mm:PinHeader_1x06_P1.27mm_Vertical | ~ |  | |
| 14 | 1 | U5 | ASDMB-32MHz | Oscillator:ASDMB-xxxMHz | Oscillator:Oscillator_SMD_Abracon_ASV-4Pin_7.0x5.1mm | ~ |  | |

Note. R6 and D1 are optional and only needed
to provide the "underglow" when powered up

## Assembly ##

All of the components, with the exception of
the headers are surface mount. How you go about
soldering these components to the board is up 
your preference.

It is substantially easier to mount the components and then mount the header pins.

A solder paste stencil for such a small board
is a minor addition to the price when
ordering if you prefer using paste and makes
assembly pretty simple.

Pay attention to the reference pins for the
oscillator and the AtMega88. Pin 1 of the
AtMega88 is to the bottom right (marked with a
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
firmware you can find it at https://github.com/dmantione/swinsid

## Configuration ##

The board has two jumpers on it:

__J1__ should be bridged for MOS _6581_ emulation or
left open for MOS _8580_.

__J2__ should be left open for MOS _8580_ emulation or
bridged for _6581_ emulation (the opposite of J1).

## Thank you ##

Thanks to Swinkels, x1541 and Tolaemon for providing
the source material that made this possible.

Swinkels' site seems to have been taken down but
a copy is held on the web archive:
https://web.archive.org/web/20220517042218/http://www.swinkels.tvtom.pl/swinsid/

Also thanks to dmantione for rescuing the source
code.
