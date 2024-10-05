# kicad-libs
KiCad Symbols and Footprints for my PCBs

## About

In this repository, I want to store the symbols and footprints
which I designed for my projects.
I also add some general notes, hints, and tips.

The official KiCad tutoral about creating [custom symbols and footprints](https://docs.kicad.org/8.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_4_custom_symbols_and_footprints)
is quite helpful.
Main takeaways
  * Symbol pins must always be aligned on a 1.27 mm (50 mil) grid
  * The exact outline is drawn on `F.Fab`, a slightly larger outline
    on `F.Silkscreen`, and the `F.Courtyard` surrounds the entire footprint
  * Distance `F.Fab` to `F.Silkscreen` should be 0.11 mm
  * Distance `F.Fab` to `F.Courtyard` should be 0.25 mm


## Local folder

You can find this repository locally under
```
~/work/pcb_design/kicad-libs
```

At least if you are Philipp 😉

## General notes

* For the resistors I usually use the P10.16 version (that is, the mounting holes are 4 x 2.54 mm apart)
* There is an overview about [standard PCB reference designators](https://www.ultralibrarian.com/2021/07/07/standard-pcb-reference-designators-to-know-ulc)

## Overview

Below is an overview of non-standard parts that are actually
standard for me as I use them so often.

### Cortex M4 TM4C123G Evaluation Board

This is my bread-and-butter evaluation board.
The footprint basically consists of 4 pin headers,
grouped in two groups of two each.
I have not yet included all pins, but only those
which I use.

Official TI page:
https://www.ti.com/tool/EK-TM4C123GXL

### Cortex M4 TM4C123GH6PM chip

This is the actual 64 pin chip, with 16 pins on each of the 4 sides.
The spacing is 0.5 mm.
Not too hard to solder even without industrial grade equipment,
given the solder mask is layed out correctly.

Facts and figures: 80 MHz, 256 KB Flash storage, 32 KB RAM, ca. 10 Euros per piece.

Datasheet:
https://www.ti.com/product/TM4C123GH6PM
