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

* For the resistors I usually use the P10.16 version (that is, the mounting holes are 4 x 2.54 mm apart),
  footprint `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal`
* THT caps
  * 100 nF (104) have footprint `Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P2.50mm`
* THT diodes
  * 5 mm has footprint `LED_THT:LED_D5.0mm`
  * Series resistors
    * 820 Ohm for 6 Volt
    * 3.9k for 12 Volt
* SMD parts
  * Resistors: 0805 `Resistor_SMD:R_0805_2012Metric`
  * Capacitors: 0805 `Capacitor_SMD:C_0805_2012Metric`
* There is an overview about [standard PCB reference designators](https://www.ultralibrarian.com/2021/07/07/standard-pcb-reference-designators-to-know-ulc)
* Testpoints
  * For firmly attaching a scope probe: Symbol `TestPoint`, Footprint `TestPoint:TestPoint_Plated_Hole_D2.0mm`
    (needs soldering)
  * For holding the probe in your hand: Symbol `TestPoint`, Footprint `TestPoint:TestPoint_Pad_2.0x2.0mm`
    (without soldering)
* Mounting holes
  * M3
  * Actual hole in `Edge.Cuts` with radius 1.9 mm
  * Courtyard with radius 3.5 mm
  * "M3" label in `F.Silkscreen`
  * Distance to edge: 4 mm
* Bar (for "not") in text is achieved via `~{CS}`
* Regular connectors (pin headers) have the symbols and footprints
  * 2 Pins: Symbol `Conn_01x02_Socket`, footprint `Connector_PinSocket_2.54mm:PinSocket_1x02_P2.54mm_Vertical`
  * 3 Pins: Symbol `Conn_01x03_Socket`, footprint `Connector_PinSocket_2.54mm:PinSocket_1x03_P2.54mm_Vertical`
  * 4 Pins: Symbol `Conn_01x04_Socket`, footprint `Connector_PinSocket_2.54mm:PinSocket_1x04_P2.54mm_Vertical`

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

The footprint has been taken over from
`Package_QFP:LQFP-64_10x10mm_P0.5mm`.
I copied it in order to being able to adapt it if necessary.

### OpAmp 4556

This is my high-current bread-and-butter OpAmp.

* Symbol `Amplifier_Operational:NJM4556A`
* Package `Package_DIP:DIP-8_W7.62mm` (for THT)
* Order for instance at [Reichelt](https://www.reichelt.de/operationsverstaerker-2-fach-dip-8-njm-4556-d-p13470.html?search=NJM+4556+D) with article no. `NJM 4556 D`

### Print connector sockets

Currently available versions
* 1x02, order e.g. at [Reichelt](https://www.reichelt.de/printstecker-einzelstecker-gerade-2-polig-pss-254-2g-p14907.html?search=PSS+254%2F2G) with article no. `PSS 254/2G`
* 1x03, order e.g. at [Reichelt](https://www.reichelt.de/printstecker-einzelstecker-gerade-3-polig-pss-254-3g-p14462.html?&trstct=pos_0&nbc=1) with article no. `PSS 254/3G`
* 1x04, order e.g. at [Reichelt](https://www.reichelt.de/printstecker-einzelstecker-gerade-4-polig-pss-254-4g-p696.html?search=PSS+254%2F4G) with article no. `PSS 254/4G`

## Parts and distributor overview

| Part           | Type       | Solder type | Distributor | Article no.    | Symbol | Package | Custom part |
|----------------|------------|-------------|-------------|----------------|--------|---------|-------------|
|                | Resistor   | THT         | Reichelt    | 122345         | bla    | blubb   | no          |
|                | Cap        | THT         | Reichelt    | 456789         | bla    | blubb   | no          |
| TM4C123GH6PMI7 | uC         | SMD         | DigiKey     | 296-44987-ND   | bla    | blubb   | yes         |
|                | Connector  | SMD         | Mouser      |                | bla    | blubb   | yes         |
