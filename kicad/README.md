# VantageF401RE — KiCad Design Files

This folder contains the complete editable **KiCad project files** for the **VantageF401RE**, a custom STM32F401RE-based evaluation and development board designed for the **Mixed Traces PCB Design Competition** by Mixed Signals, Electronics Association of MEC.

The design was developed entirely in **KiCad** as a **2-layer PCB**, with a focus on functionality, accessibility, protection, compact organization, and practical embedded-system development.

---

## Project Files

| File | Description |
|------|-------------|
| `VantageF401RE.kicad_pro` | Main KiCad project file |
| `VantageF401RE.kicad_sch` | Complete electrical schematic |
| `VantageF401RE.kicad_pcb` | Final 2-layer PCB layout |

These files can be opened and edited using KiCad.

---

## Board Specifications

| Parameter | Specification |
|-----------|---------------|
| MCU | STM32F401RET6 |
| MCU Package | LQFP-64 |
| PCB Layers | 2 |
| Board Size | 80 mm × 60 mm |
| Design Tool | KiCad |
| USB Interface | USB Type-C, USB 2.0 |
| Supply Voltage | 3.3 V regulated |
| External Input | 5 V |
| Debug Interface | SWD |
| Oscillator | 8 MHz external crystal |

The board size remains well within the competition's maximum permitted **100 mm × 100 mm** area.

---

## Main Functional Blocks

The VantageF401RE integrates the following functional sections:

### 1. STM32F401RET6 Core

The STM32F401RET6 serves as the main processing device.

The design includes:

- External 8 MHz crystal oscillator
- VCAP1 capacitor
- MCU power decoupling
- Analog supply decoupling
- Reset circuitry
- BOOT0 configuration
- Dedicated programming/debug access

---

### 2. Power Management

The power section provides a regulated 3.3 V supply for the MCU and peripherals.

Features include:

- USB-C 5 V input
- External 5 V input
- AP2112K-3.3 LDO regulator
- Input and output capacitors
- Schottky-diode protection for external 5 V input
- Power LED
- 3.3 V and GND test points

---

### 3. USB Interface

A USB-C connector is provided for USB 2.0 connectivity and 5 V power input.

The USB section includes:

- USB Type-C receptacle
- USB D+ and D− connections
- CC1 and CC2 resistors
- USB ESD protection using USBLC6-2SC6
- USB data-line series resistors
- USB status LED
- Dedicated USB 5 V power rail

The USB data path is protected before reaching the STM32 USB pins.

---

### 4. SWD Programming and Debugging

A dedicated 5-pin SWD header is provided for programming and debugging the STM32.

The interface exposes:

- VCC
- SWDIO
- GND
- SWCLK
- NRST

Test points are also provided for SWDIO, SWCLK, and NRST.

---

### 5. Reset and Boot Configuration

The board provides dedicated controls for reliable startup and debugging.

Features include:

- Hardware reset push button
- NRST pull-up resistor
- BOOT0 pull-down resistor
- BOOT selection header

---

### 6. Communication Interfaces

Dedicated headers are provided for commonly used embedded communication protocols.

#### UART

- UART TX
- UART RX
- 3.3 V
- GND

#### SPI

- SPI SCK
- SPI MISO
- SPI MOSI
- SPI CS
- 3.3 V
- GND

#### I²C

- I²C SCL
- I²C SDA
- 3.3 V
- GND
- Dedicated pull-up resistors

---

### 7. GPIO Expansion

A dedicated **2×10 GPIO header** provides convenient access to multiple STM32 GPIO pins along with power and ground connections.

This allows external sensors, displays, modules, and other peripherals to be connected directly to the board.

---

### 8. User Interface

The board includes:

- User push button
- User LED
- Reset button
- Power LED
- USB status LED
- BOOT selection header

These provide basic interaction and visual feedback during development and debugging.

---

### 9. Clock and Decoupling

The MCU clock section uses an external **8 MHz crystal oscillator** with dedicated load capacitors.

The power network includes:

- Local 100 nF MCU decoupling capacitors
- Bulk 4.7 µF decoupling
- Analog supply filtering
- VCAP1 capacitor
- Regulator input/output capacitors

The decoupling components were placed close to their respective power pins and functional blocks during PCB layout.

---

### 10. Test and Debug Access

Dedicated test points are provided for important signals:

- 3.3 V
- GND
- SWDIO
- SWCLK
- NRST

These improve accessibility for oscilloscope probing, debugging, and laboratory measurements.

---

## PCB Layout

The final PCB uses a **2-layer copper stack-up** with an **80 mm × 60 mm** board outline.

The placement was organized into functional regions, including:

- Central STM32 MCU section
- USB and power section near the board edge
- SWD/debug section
- Communication interface headers
- GPIO expansion
- Clock circuitry
- User-control section
- Power indication
- Test points

Ground planes are used to provide continuous ground-return paths and improve overall PCB organization.

The layout was routed while considering component accessibility, signal paths, power distribution, and the physical constraints of a 2-layer board.

---

## Design Verification

The final schematic and PCB were verified using KiCad's electrical and PCB design-rule checking tools.

### ERC

**Electrical Rules Check:**

- Violations: **0**
- Errors: **0**
- Warnings: **0**

### DRC

**Design Rules Check:**

- Reported violations: **0**
- Errors: **0**
- Intentional exclusions: **4**

The intentional exclusions correspond to reviewed USB-C connector mechanical hole-clearance checks associated with the selected footprint.

Detailed ERC and DRC reports are available in the repository's [`results/`](../results/) directory.

---

## Design Approach

The VantageF401RE was designed as a complete development platform rather than only an STM32 breakout board.

The design combines:

**Processing + Power + USB + Debugging + Communication + Expansion + User Interface + Protection**

within a compact 2-layer PCB.

Particular attention was given to:

- Power integrity
- Local decoupling
- USB protection
- Signal accessibility
- Debug accessibility
- Peripheral expansion
- Component placement
- Ground connectivity
- PCB manufacturability
- Design-rule compliance

---

## Related Repository Folders

The complete project is organized into dedicated sections:

### [`bom/`](../bom/)

Contains the component selection and BOM documentation.

### [`docs/`](../docs/)

Contains project documentation, including:

- Major design decisions
- Initial block diagram
- Progress evaluation documentation

### [`results/`](../results/)

Contains the final ERC and DRC verification reports.

### [`gerbers/`](../gerbers/)

Contains the final Gerber and drill files prepared for PCB fabrication.

### [`pdf/`](../pdf/)

Reserved for the final project documentation PDF.

---

## Opening the Project

To inspect or continue development:

1. Install a compatible version of KiCad.
2. Open `VantageF401RE.kicad_pro`.
3. Open the schematic through the KiCad project manager.
4. Open the PCB layout from the same project.

The `.kicad_sch` and `.kicad_pcb` files can also be opened individually when required.

---

## Final Design Status

The VantageF401RE design has completed:

- Component selection
- Schematic development
- PCB component placement
- PCB routing
- Power-system implementation
- USB interface implementation
- SWD interface implementation
- UART, SPI and I²C interfaces
- GPIO expansion
- User interface circuitry
- PCB design-rule verification
- Schematic electrical-rule verification
- Gerber and drill-file generation

The files in this directory represent the **final editable KiCad design** submitted as part of the project.

---

**Project:** VantageF401RE  
**MCU:** STM32F401RET6  
**PCB:** 2-Layer, 80 mm × 60 mm  
**EDA Tool:** KiCad  
**Status:** Final Design Completed
