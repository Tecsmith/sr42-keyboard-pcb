# SR42 Keyboard PCB

<p align="center"><img alt="Do not build" src="docs/donotbuild.min.svg" width="213"></p>
<blockquote align="center"><b>NB:</b> This project design is complete, but has not been prototyped for validation.</blockquote>

## Intent

A 42-key micro keyboard designed for QMK with specific focus on ultra fast key scan rates / poll rates to make for an ideal gaming keyboard.

#### Progression

- See [CHANGELOG.md](CHANGELOG.md)

## Case

This case is designed in conjunction with the [SR42 Keyboard Case](https://github.com/tecsmith/sr42-keyboard-case).  These two projects are mutually inclusive and built as one solution.

<p align="center"><img src="docs/sr42-case.png" width="480"></p>

## Resources

### Schematic
 - PDF [here](docs/sr42-revB.pdf)

### MCU PCB
 - EAGLE BRD *(PCB)* [here](EAGLE/sr42/sr42-revB-kbd.brd)
 - EAGLE SCH *(Schematic)* [here](EAGLE/sr42/sr42-revB-kbd.sch)

### Key Switch PCB
 - EAGLE BRD *(PCB)* [here](EAGLE/sr42/sr42-revB-kbd.brd)
 - EAGLE SCH *(Schematic)* [here](EAGLE/sr42/sr42-revB-kbd.sch)


### Beta PCB renders

#### Top

<p align="center"><img src="docs/sr42-revB-top.png" width="640"></p>

#### Bottom *(Component side)*

<p align="center"><img src="docs/sr42-revB-btm.png" width="640"></p>

#### Intra-Board Connectors

You will need 3x Molex Pico-EZMate cables

|                                                                 | Cable | Usage                                |
|:---------------------------------------------------------------:|:-----:|:-------------------------------------|
| <img src="docs/pico-ezmate-6.png" width="64" height="64"></img> | 6 way | Keyboard Matrix SPI interface        |
| <img src="docs/pico-ezmate-4.png" width="64" height="64"></img> | 4 way | USB connection to UBD                |
| <img src="docs/pico-ezmate-3.png" width="64" height="64"></img> | 3 way | ARGB to drive status & per-key LED's |


### Layout ideation renders

#### Render

<p align="center"><img src="docs/sr42-render.png" width="640"></p>

#### Layout

<p align="center"><img src="docs/sr42-layout.png" width="640"></p>

#### Matrix coordinates *(QMK & VIA)*

<p align="center"><img src="docs/sr42-matrix.png" width="640"></p>


## Planned Features

- [ ] QMK / VIA build
- [ ] 1x `STM32F405` STM32 CPU *(ft. dual USB, one is FS, the other HS)*
- [ ] 1x `TS3USB221` USB 2.0 Multiplexer for USB port selection *(based on [akeypad](https://github.com/luantty2/akeypad) )*
- [ ] 1x `USB3300-EZK` Hi-Speed USB Host for OTG PHY pin interface
- [ ] ~~1x `W25Q64JW` 8K SPI Flash Module~~ *[Not needed, the MCU has 512K Flash]*
- [ ] 1x `M95640-DRE` 8K SPI EEPROM Module
- [ ] 6x `MC74HC589A` SPI Input Shift Registers
    - No QMK key matrix, using all direct pins for faster scan rates
    - Scan via individually grounded keys on shift registers
- [ ] 2x `IS31FL3746B` SPI LED Matrix Drivers
    - 43x RGB LED's
    - With power on/off `TPS22995H-Q1` load switchs, 1 per
- [ ] C4 *(or S1)* UDB USB-C by @ai03 - see [here](https://github.com/ai03-2725/Unified-Daughterboard)


## Possible BIG issues

- [x] ~~With very limited PCB space, 13x IC's may not fit :(~~ *[Resolved with separate key and MCU PCB's]*
- [ ] ~~Not sure QMK can handle High Speed USB~~ *[It can, just now need to do it :( )]*
- [ ] Not sure dual USB is switchable with the USB multiplexer *[Needs to be coded for and tested]*
    - FS USB required for Bootloader
    - HS USB required for >1KHz polling rates


&nbsp;<br>&nbsp;
---
Made with :heart: by **Silvino Rodrigues**