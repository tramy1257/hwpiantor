# hwpiantor

_3D Printed, Handwired, Piantor Style Keyboard_
<p float="left">
  <img src="/img/main-img.jpg" alt="drawing" width="400"/>
  <img src="/img/wiring.jpg" alt="drawing" width="400"/>
</p>


## Overview
I made this keyboard to tryout the Piantor/Cantor layout with parts I already have at home.

The goal is to show off as much DIY elements as possible. Eventually, the back cover will be replaced with a clear acrylic cover to show off the wiring.

## BOM
* 42 x MX Switches
* 42 x diodes
* 5 x 6mm M2 standoffs
* 10 x 5mm M2 button head screws*
* 4 x M2 nuts
* 4 x 6mm M2 button head screws**
* 2x Raspberry Pi Pico or Pico 2
* 2 x TRRS sockets
* Rubber feets (Optional)

**Socket head screws work as well. They have higher heads, which will stick out of the bottom of the case. But if you're using rubber feets, it should not be a problem.*

***Any screw length from 6mm to 12mm should work. Button head screws work fine here.*

## Building

### I. 3D Printing
[Printing the case and plate](./printing/README.md)

[Printed keycaps by Joe Scotto](https://github.com/joe-scotto/scottokeebs/tree/main/Extras/ScottoCaps/Scooped/MX)

### II. Preparing the plate for soldering
Screw the **6mm standoffs** to the underside of the plate with **5mm M2 screws**

<img src="/img/plate-screw.png" alt="drawing" width="400"/>

Add the **M2 nuts** to the underside of the plate for securing the Pi Pico

<img src="/img/plate-nuts.png" alt="drawing" width="400"/>

Solder the pin headrs to the Pi Pico. Then screw the Pi Pico to the plate with **6mm M2 screws** (Any screw length from 6mm to 12mm should work). The pin headers legs should stick through the 2 tracks on the plate

<img src="/img/pico-screw.png" alt="drawing" width="400"/>

Glue the TRRS socket to the plate.

<img src="/img/trrs.png" alt="drawing" width="400"/>


### III. Soldering the switches and the Pico
Checkout [Joe Scotto's video on how to handwire a keyboard](https://www.youtube.com/watch?v=hjml-K-pV4E) if you don't know how wiring work yet.

This is how my switches are wired. If you choose to use different pins, make sure you update them in the firmware file later.

<img src="/img/switches-wiring.jpg" alt="drawing" width="400"/>

To connect the 2 Pi Picos, follow this wiring diagram. It does not matter which pin on the TRRS socket you wire the Pico's pins to. Both sides wiring just need to match exactly. Once you're done soldering both TRRS sockets, it is a good idea to connect the halves and check the Picos' pins continuity with a multimeter.

<img src="/img/trrs-wiring.jpg" alt="drawing" width="400"/>

### IV. Assembling the keyboard
Finally, screw the plate and the case together using **5mm M2 screws**

## Firmware
I used KMK firmware configured with [Pog](https://pog.janlunge.de/) v2.0.4. I have not had a chance to test the firmware on a different keyboard yet, but here's how to install the firmware:

### KMK only
1. Install KMK Firmware on both Picos: [KMK > Getting Started](https://github.com/KMKfw/kmk_firmware/blob/main/docs/en/Getting_Started.md)
2. Rename the left Pico drive to PIANTORHWL and the right Pico drive to PIANTORHWR
2. Copy the files in [kmk-firmware > left](./kmk-firmware/left/) to the left Pico and [kmk-firmware > right](./kmk-firmware/right/) to the right Pico.
3. Make sure you update:
    1. The row and column pins in both **pog.json** files if you have different wiring
    2. The keymaps in the right **pog.json** file for different keymap
1. The keyboard should work now but configuring keymaps without Pog can be tedious

### Using Pog
Using Pog will let you remap you keys easier. NOTE: I used Pog v2.0.4 so it may not work for future Pog versions
1. Follow the same steps above.
3. Connect the right half to the computer
2. Install [Pog](https://pog.janlunge.de/) on your computer
1. Open Pog > Add Keyboard > Add Existing Pog Keyboard > Select the pog.json file for the right Pico drive
1. You can then configure the keyboard layout, row and column pins using Pog
