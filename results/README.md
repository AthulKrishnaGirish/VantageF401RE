# VantageF401RE — Final Verification Results

## Overview

The **VantageF401RE** is a custom STM32F401RE-based 2-layer evaluation and development board designed as part of the **Mixed Traces PCB Design Competition** conducted by **Mixed Signals, Electronics Association of MEC**.

The design was developed from the ground up in **KiCad**, with emphasis on electrical correctness, signal accessibility, power integrity, protection, usability, compact PCB organization, and practical embedded-system development.

This folder contains the final **Electrical Rules Check (ERC)** and **Design Rules Check (DRC)** results for the completed design.

---

## Final Verification Status

The completed schematic and PCB layout were subjected to KiCad's electrical and physical design-rule verification.

### Electrical Rules Check — ERC

The final schematic achieved:

- **ERC Violations: 0**
- **Errors: 0**
- **Warnings: 0**

This confirms that the completed schematic passed the electrical rules check without reported violations.

### Design Rules Check — DRC

The final PCB achieved:

- **DRC Errors: 0**
- **Known DRC Violations: 0**
- **Intentional Exclusions: 4**

The four exclusions correspond to reviewed USB-C connector mechanical hole-clearance checks associated with the selected connector footprint.

The exclusions were intentional and reviewed during the final PCB verification process.

---

## What We Achieved

The VantageF401RE design was developed as a complete, functional STM32 development-board platform rather than a minimal MCU breakout.

### Core Processing

- **STM32F401RET6** ARM Cortex-M4 microcontroller
- 512 KB Flash
- 96 KB SRAM
- Up to 84 MHz operating frequency
- External 8 MHz crystal oscillator
- Dedicated VCAP and power decoupling

### Power System

- USB-C 5 V power input
- External 5 V input
- Schottky-diode protected external supply path
- AP2112K 3.3 V low-dropout regulator
- Separate input and output bulk decoupling
- Dedicated MCU power decoupling
- Analog supply decoupling
- Power indication LED
- Accessible 3.3 V and GND test points

### Programming and Debugging

- Dedicated **SWD interface**
- SWDIO
- SWCLK
- NRST
- VCC
- GND
- Dedicated reset push button
- BOOT0 configuration header
- BOOT0 pull-down

### Communication Interfaces

The board provides dedicated headers for:

- **UART**
- **SPI**
- **I²C**

This allows the board to interface easily with external sensors, displays, memories, communication modules, and other embedded peripherals.

### USB Interface

The board incorporates a USB-C interface with:

- USB 2.0 D+ and D− connectivity
- CC1 and CC2 configuration resistors
- Dedicated USB ESD protection
- USB differential-pair routing
- Series termination resistors
- USB status indication
- USB 5 V power extraction

### User Interface

- Dedicated user push button
- User LED
- Reset button
- Power LED
- USB status LED
- BOOT selection header

### Expansion

A dedicated **2×10 GPIO header** exposes multiple STM32 GPIOs along with power and ground connections, providing convenient access for external hardware and experimentation.

### Debugging and Measurement

Dedicated test points are provided for:

- 3.3 V
- GND
- SWDIO
- SWCLK
- NRST

These improve accessibility during debugging, probing, and laboratory testing.

---

## Engineering Decisions

The design was developed with emphasis on more than simply satisfying the mandatory competition requirements.

Key design considerations included:

- Central placement of the STM32 MCU for organized routing
- Short and direct USB protection path
- Dedicated USB power and data sections
- Localized power regulation circuitry
- Appropriate MCU decoupling
- Dedicated analog supply filtering
- Crystal oscillator placed close to the MCU
- Dedicated SWD access
- Accessible peripheral headers
- Ground planes for improved return-current paths
- Structured separation of functional PCB regions
- Compact **80 mm × 60 mm** board outline
- Two-layer PCB implementation

---

## Design Validation

The final design was checked at both schematic and PCB levels.

### Schematic Validation

ERC was performed on the completed schematic to identify:

- Electrical connectivity issues
- Unconnected or incorrectly connected pins
- Power-related rule violations
- Driver conflicts
- Other schematic-level rule violations

**Final result: 0 ERC violations.**

### PCB Validation

DRC was performed on the completed PCB to identify:

- Clearance violations
- Track and pad rule violations
- Copper connectivity problems
- Board-edge violations
- Unrouted connections
- Other PCB design-rule violations

**Final result: 0 reported DRC violations**, with 4 reviewed intentional exclusions related to USB-C connector mechanical clearances.

---

## Design Strengths

VantageF401RE combines the core functionality expected from an STM32 development platform with additional practical features that improve its usefulness as a development and experimentation board.

The design integrates:

- USB-C connectivity
- Protected USB data lines
- Regulated 3.3 V power
- External 5 V input
- SWD debugging
- BOOT configuration
- UART
- SPI
- I²C
- GPIO expansion
- User controls
- Multiple indicators
- Test points
- Crystal oscillator
- Dedicated power filtering
- Ground planes

This provides a broader and more practical development environment while remaining within the competition's **2-layer PCB** and **100 mm × 100 mm maximum board-size** constraints.

---

## Final Design Outcome

The project progressed from the initial concept and block-level planning through component selection, schematic development, PCB placement, routing, verification, and fabrication-file generation.

The completed design now includes:

**Concept → Component Selection → Schematic → PCB Layout → Routing → ERC/DRC Verification → Gerber Generation**

The final design files are provided in the repository for inspection and further development.

---

## Repository Contents

### `kicad/`

Contains the complete editable KiCad project:

- Schematic
- PCB layout
- KiCad project file

### `bom/`

Contains the component-selection and BOM documentation.

### `docs/`

Contains project documentation including:

- Major design decisions
- Initial block diagram
- Progress evaluation documentation

### `results/`

Contains the final ERC and DRC verification reports.

### `gerbers/`

Contains the generated Gerber and drill files packaged for PCB fabrication.

### `pdf/`

Reserved for the final project documentation PDF.

---

## Final Statement

**VantageF401RE represents a complete, verified, and fabrication-ready PCB design developed in KiCad around the STM32F401RET6.**

The design focuses on:

**Functionality • Reliability • Accessibility • Protection • Verification • Practical Embedded Development**

The final ERC and DRC results provide documented verification of the completed schematic and PCB design, while the complete KiCad project and fabrication files are provided for transparency and evaluation.
