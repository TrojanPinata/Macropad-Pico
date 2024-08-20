# Macropad-Pico

This is a 12-key macropad based off of the Raspberry Pi Pico with the intention of making something which is almost entirely 3d printable, cheap, and designed with the intention to show off the board, keycaps, and switches. Some key features of this board is the window for the microcontroller, center (separate) USB-C connector (with detachable cable), and a completely through-hole design.

This board is intended for people who want to be able to do the majority of the project on their own - only requiring you to send out the PCB to be made if you want to use one. A alternate switchplate is included for those wanting to handwire their boards.

## What you need

In order to actually make this you will need a few things (assuming you didn't get this as a kit and nothing is preassembled):

   - A soldering iron (+ flux, sponge, etc.)
   - A small phillips screwdriver
   - 4 ~12mm long M2 screws/bolts
   - A [USB-C female breakout board](https://a.co/d/hSMmR2M)
   - Some ~26 AWG wire
   - 12 1N4148 Diodes (or similar speed switching diodes)
   - 12 keyboard switches
   - 12 keycaps
   - A Pi Pico
   - The 3D printed case and switchplate
   - A USB-C cable
   - The provided firmware
   - The PCB (optional)
   - Male/Female 4-pin JST connectors (PH type) (optional, but recommended)

## Preparation 

(If you got this as a kit then this section can be mostly disregarded)

First thing is first, the case and switchplate will need to be printed. This size of this macropad is small enough to be printable on any 3D printer, so it should be pretty accessible. Be aware that tolerances and some shrink of the printed components is normal and should be accounted for. I printed mine with PLA, though most anything can be used. I made the switchplate at 100% infill and the case at 25% and they came out fine.

If you are using the PCB, then you can take the gerbers and send them off to JLCPCB or somewhere and get them made. The PCBs should cost ~$12 with shipping, don't overpay.

If you are doing this with a stock Pi Pico you might have clearance issues with the Micro USB port as it protrudes out a bit. It should fit with a slight bulge (0.1mm too high +/- 0.3mm) - this is mostly a remnant due to using a [Pico I designed myself](https://github.com/TrojanPinata/Pico) which does not have this issue. Shaving down the plate fixes this but it should not get in the way as long as the Pico is soldered down flat.

In this step I also recommend making the JST connectors. If you are using a PCB, cut down the pins on the female port before soldering them down, making sure they are flush on both sides so that the Pico will be flat when it is soldered down. This port will make the case and PCB easlily seperable when trying to do work on it. Making the JST connectors is kind of a mess, but watch a tutorial and be patient as to not mess them up. We will cover soldering the USB port to them in the next section.

## Building the board

At this point, you have everything in ready to be soldered, glued, and assembled. We will start by going over the soldering.

If you have never soldered anything before let me give you some tips to be successful:
   
   - Tin all wires before soldering. When soldering the wire to the thing, you shouldn't need that much as the wire already has some on the tip and will easily attach to the hole/pad.
   - Use flux. Liquid flux, flux pen, doesn't matter - this will make it way easier to make the solder stick.
   - Clean your iron tip with brass brush. This will get rid of the burn off which will make the solder not melt to the tip.
   - Don't let the iron get too hot, stay around 280C for lead-free solder. 
   - Use whatever tip you are comfortable with, the smaller the more percise, but somewhere a bit larger may be easier for beginners.

To start, if you haven't attached the female JST connector to the board (ignore if kit), put the connector on the board and mark how much extra wire pokes through the other side of the board, and cut the remainder. Then put some flux in the holes with the connector and solder, using just enough to fill the hole and not create a large bump.

Since we are working on that, then it is probably also necessary to solder the USB port now. The terminals are labeled on both the board and connector, so make sure to match them up. Use flux and tinned wire, and don't leave the iron on the pads too long - only enough to reflow the solder from the tinned wires to the breakout board.

With this, the connector is done and the Pico can be soldered down. To do this, the easiest way is to flatten the Pico in place on the board (if it doesn't want to stay then use tape temporarily) and solder the corners to their pads, then go back and get all of the pads in the middle. Use flux and use a amount of solder to connect the top of the pad with the PCB. On the bottom of the board, there is a cutout for accessing the TP2 and TP3 pads. I recommend soldering two short lengths of wire to them before putting the Pico down, as it makes access to them slightly easier, but it can be done after. Connect those wires to the DP and DN holes to the left on the backside of the PCB. 

After doing that, you can drop the diodes in, verifying that they are in the proper orientation. Bend the legs out a bit, and flip the board over. They should stay in, but also the surface below should keep pressure on them so they are flat on the front side. Flux, solder, then clip the legs off (protect your eyes!). 

At this point, you are almost done. You now need to pop your switches into the switchplate, and try to fanagle the switches in the array into the holes on the PCB. This is tricky, but be patient. Once they are all in, solder the pins in. The PCB and switchplate should now be sort of connected via the switches.

At this time, you should glue the USB-C connector into the case and connect it to the PCB. Then, the PCB-switchplate combo should be dropped into the case and screwed in. With that, you are ready to flash the firmware and put on the keycaps.

## Firmware

I will not go over building your own firmware here, as that is far outside the scope of this guide. The firmware provided can be flashed to the pico but plugging in the PCB or Pico to a computer while holding the `BOOTSEL` button and dragging the provided `.uf2` file onto the drive that `RPI-RP2` drive that appears. This will flash the board and you will be ready to go.

