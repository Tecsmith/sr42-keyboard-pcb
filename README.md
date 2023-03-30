# VR42-Keyboard-PCB

> &#128679; Placeholder for future project &#128679;

![](docs/vr42-layout.svg)

![](docs/vr42-render.png)

## Intent

A 42-key micro keyboard designed for QMK with specific focus on ultra fast key scan rates / poll rates to make for an ideal gaming keyboard.

## Planned Features

- [ ] QMK / Vial build
- [ ] 1x `STM32F415` STM32 CPU *(ft. dual USB, one is FS, the other HS)*
- [ ] 1x `TS3USB221` USB 2.0 Multiplexer for USB port selection *(based on [akeypad](https://github.com/luantty2/akeypad) )*
- [ ] ~~1x `W25Q64JW` 8K SPI Flash Module~~
- [ ] 1x `M95640-DRE` 8K SPI EEPROM Module
- [ ] 6x `MC74HC589A` SPI Input Shift Registers
    - No QMK key matrix ... scan via individually grounded keys on shift registers
- [ ] 2x `IS31FL3746B` SPI LED Matrix Drivers
    - 43x RGB LED's
    - with power on/off MOSFET or latch circuit
- [ ] C4 *(or S1)* UDB Usb-C - see: https://github.com/ai03-2725/Unified-Daughterboard

## Possible BIG issues

- With very limited PCB space, 13x IC's may not fit :(
