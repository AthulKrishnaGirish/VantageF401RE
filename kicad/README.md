# Verification Results

This folder contains the final verification results for the **VantageF401RE** STM32F401RE-based evaluation and development board.

## Design Verification

The completed schematic and PCB layout were verified using KiCad's electrical and design rule checking tools.

### ERC — Electrical Rules Check

The final schematic was checked using KiCad ERC.

- **ERC Violations: 0**
- **Errors: 0**
- **Warnings: 0**

This confirms that the final schematic passed the electrical rules check without reported violations.

### DRC — Design Rules Check

The final PCB layout was checked using KiCad DRC.

- **DRC Errors: 0**
- **Known DRC Violations: 0**
- **Intentional Exclusions: 4**

The intentional exclusions correspond to known USB-C connector mechanical hole-clearance checks and were reviewed as acceptable for the selected connector footprint.

## Final Design Status

The VantageF401RE schematic and PCB layout have been completed and verified.

The final design includes:

- STM32F401RET6 microcontroller
- 2-layer PCB
- USB-C power and USB 2.0 interface
- 3.3 V regulated power supply
- SWD programming and debugging interface
- Reset and BOOT selection
- UART interface
- SPI interface
- I²C interface
- GPIO expansion
- User button
- User LED
- Power LED
- USB status LED
- USB ESD protection
- External 5 V input
- Crystal oscillator
- Test points
- MCU and analog power decoupling
- Ground planes

The final KiCad schematic and PCB design files are available in the [`kicad/`](../kicad/) directory.

Gerber and drill files are available in the [`gerbers/`](../gerbers/) directory.
