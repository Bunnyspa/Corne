# Corne

[Corne](https://github.com/foostan/crkbd) V3 keyboard with various features to achieve:
- Low PCB print cost (i.e. reversibility)
- Easy hand soldering
- Symmetry

## Warning
I have **NOT** tested the PH 2.0mm battery connector yet. Let me know if it works.

## Features
- MX, Choc V1, and Choc V2 switch support
- Wired and wireless support
- Reversible PCB
- Through-hole and SMD diode support
- Default pinouts (i.e. you can use the default QMK or ZMK firmware)

### Wired
- OLED display support
- 6-pin USB-C as keyboard link

### Wireless
- nice!view support
- PH 2.0mm (and just plain through-hole pads) for battery
- Power switch at the north side, either front or back (your choice)

## Design Choice Explanation

### Keyboard link
- The 6-pin version is used for easier hand soldering
- TRRS is not used due to the lack of symmetry
- 
### OLED pinout location is slightly to the left
- To counter the OLEDs having the display area slightly to the right
- To overlap nice!view pinout location

## Jumper Soldering

![Solder example](https://github.com/Bunnyspa/Corne/blob/main/resources/solder_example.jpg?raw=true)
![Above image in KiCad](https://github.com/Bunnyspa/Corne/blob/main/resources/solder_example_kicad.jpg?raw=true)
The images above shows the backside.

To support the PCB reversibility, jumper pads are added (pretty much everywhere). The through-hole solder pads themselves are not connected to anything, so you need to connect jumpers together where you solder the pads.

### Display

For nice!view, you must connect the upper jumper pad (right side in the picture).

For 4-pin I2C OLEDs, you must connect the lower jumper pad (left side in the picture).

## IRL Testing
This PCB worked in my testing with the wireless configuration (per side):
- Solder PCB from JLCPCB
- nice!nano
- nice!view 3rd-party alternative (Taobao)
- 750mAh battery
- SPDT switch for power switch
- Tactile switch for reset switch
- Choc V2 switches
- Default ZMK Corne + nice!view firmware

I also tried Pro Micro + OLED combo with QMK, and they worked fine. (I did not fully build the Corne for this one. Just the MCU and the display.)

I have **NOT** tested the PH 2.0mm battery connector yet. Let me know if it works.

## Warning for Custom Firmware
The bottom 4 of MCU board pinouts do not support reversibility (hence no jumper pads). If your custom firmware uses these pins, you should configure pinouts for each side properly.

## PCB Preview
| Solder  | Hotswap |
| - | - |
| ![Solder version front preview](https://github.com/Bunnyspa/Corne/blob/main/resources/corne-solder-3d-front.jpg?raw=true) ![Solder version back preview](https://github.com/Bunnyspa/Corne/blob/main/resources/corne-solder-3d-back.jpg?raw=true) | ![Hotswap version front preview](https://github.com/Bunnyspa/Corne/blob/main/resources/corne-hotswap-3d-front.jpg?raw=true) ![Hotswap version back preview](https://github.com/Bunnyspa/Corne/blob/main/resources/corne-hotswap-3d-back.jpg?raw=true) |