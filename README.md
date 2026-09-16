# VantageF401RE

### STM32F401RE Evaluation & Development Board

**Mixed Traces PCB Design Competition — 2026**
**Mixed Signals — Electronics Association of MEC**

---

## Project Overview

**VantageF401RE** is an independently designed, compact **2-layer STM32F401RE-based evaluation and development board** developed in KiCad as part of the **Mixed Traces PCB Design Competition 2026**.

The board is built around the **STM32F401RET6** microcontroller and integrates the essential features expected from a development board, including regulated power, USB connectivity, SWD programming/debugging, UART, SPI, I²C, GPIO expansion, reset and boot control, user indicators, and supporting protection and decoupling circuitry.

The design was developed independently with the **STM32 NUCLEO-F401RE** used as a functional and architectural reference. The VantageF401RE schematic, component arrangement, PCB placement, and routing were independently developed and are not a direct copy of the NUCLEO PCB layout.

---

## Project Status

### Completed — Final Design

The VantageF401RE schematic and PCB layout have been completed in KiCad.

The project includes:

- Complete STM32F401RET6-based schematic
- Power supply and 3.3 V regulation
- USB-C power and USB 2.0 interface
- USB ESD protection
- SWD programming/debugging interface
- UART interface
- SPI interface
- I²C interface
- GPIO expansion
- Reset and BOOT selection circuitry
- User button and LED
- Power and USB status indicators
- External 5 V input
- Crystal oscillator
- MCU power decoupling
- Test points
- Two-layer PCB layout
- Ground copper zones
- ERC and DRC verification
- Final Gerber and drill file generation
- Final component list and design documentation

The final PCB design achieved **0 reported DRC errors**, and the final manufacturing files were generated from the completed PCB layout.

> **Note:** The project was developed and verified as a PCB design in KiCad. No physical fabrication or hardware testing is claimed as part of this submission.

---

## Key Specifications

| Parameter | Specification |
|---|---|
| **Board Name** | VantageF401RE |
| **MCU** | STM32F401RET6 |
| **MCU Package** | LQFP-64 |
| **PCB Layers** | 2 copper layers |
| **PCB Dimensions** | 80 mm × 60 mm |
| **Design Software** | KiCad |
| **Logic Supply** | 3.3 V |
| **USB Interface** | USB Type-C / USB 2.0 |
| **Programming & Debugging** | SWD |
| **Communication Interfaces** | UART, SPI, I²C |
| **GPIO Expansion** | 20-pin header |
| **External Power** | 5 V input |
| **PCB Verification** | ERC / DRC |
| **Fabrication Requirement** | Not required |

---

## Main Features

### 1. STM32F401RET6 Core

The board uses the **STM32F401RET6**, a 64-pin LQFP STM32F4-series microcontroller.

The MCU section includes:

- 3.3 V digital supply
- Analog supply connection
- VCAP capacitor
- Local decoupling capacitors
- External HSE crystal
- Reset circuitry
- BOOT0 configuration
- SWD programming/debugging access

---

### 2. Power Supply

The board provides a regulated **3.3 V supply** for the STM32F401RET6 and peripheral circuitry.

**Power inputs**

- USB-C 5 V input
- External 5 V input

**Regulation**

An **AP2112K-3.3 LDO regulator** converts the incoming 5 V supply to 3.3 V.

The power section includes:

- Input decoupling
- Output decoupling
- 3.3 V bulk capacitance
- Power indication
- External-input protection

An **SS14 Schottky diode** is included on the external 5 V input path for protection.

---

### 3. USB-C Interface

The board provides a USB Type-C connector for power and USB 2.0 data connectivity.

The USB section includes:

- USB-C receptacle
- USB 2.0 D+ and D− connections
- CC1 and CC2 configuration resistors
- USB ESD protection
- USB D+ and D− series resistors
- USB status indicator

The USB data path uses the STM32F401RE USB pins:

- **PA11 — USB_DM**
- **PA12 — USB_DP**

---

### 4. USB ESD Protection

A **USBLC6-2SC6** protection device is placed close to the USB connector.

The protection network is incorporated into the USB data path to provide ESD protection for the USB D+ and D− lines.

The USB signal path is organized as:

```text
USB-C
  ↓
USB D+ / D−
  ↓
USB ESD Protection
  ↓
22 Ω Series Resistors
  ↓
STM32F401RET6
```

---

### 5. SWD Programming & Debugging

A dedicated 5-pin SWD header is provided for programming and debugging the STM32F401RET6.

The interface provides:

- VCC
- SWDIO
- GND
- SWCLK
- NRST

MCU connections:

- PA13 — SWDIO
- PA14 — SWCLK
- NRST — Reset

Dedicated test points are also provided for SWDIO, SWCLK, and NRST.

---

### 6. UART Interface

A dedicated 4-pin UART header provides easy access to the serial communication interface.

| UART Signal | MCU Pin |
|---|---|
| UART_TX | PA2 |
| UART_RX | PA3 |
| VCC | +3V3 |
| GND | GND |

---

### 7. SPI Interface

A dedicated 6-pin SPI header is provided.

| SPI Signal | MCU Pin |
|---|---|
| SPI_SCK | PA5 |
| SPI_MISO | PA6 |
| SPI_MOSI | PA7 |
| SPI_CS | PA4 |
| VCC | +3V3 |
| GND | GND |

---

### 8. I²C Interface

A dedicated 4-pin I²C header is provided with external pull-up resistors.

| I²C Signal | MCU Pin |
|---|---|
| I2C_SCL | PB6 |
| I2C_SDA | PB7 |
| VCC | +3V3 |
| GND | GND |

Two 4.7 kΩ pull-up resistors are provided for the I²C lines.

---

### 9. GPIO Expansion

A dedicated 20-pin GPIO expansion header provides access to multiple STM32 GPIOs along with power and ground.

The expansion header provides access to signals including:

- PA0
- PA1
- PA8
- PA9
- PA10
- PB2
- PB10
- PC6
- PB12–PB15
- PC0–PC5
- +3V3
- GND

This provides flexibility for connecting external sensors, modules, displays, and other peripherals.

---

### 10. Reset & Boot Control

**Reset**

The NRST line includes:

- 10 kΩ pull-up resistor
- Dedicated reset pushbutton
- SWD NRST connection
- NRST test point

**Boot Selection**

BOOT0 includes:

- 10 kΩ pull-down resistor
- Dedicated BOOT selection header
- +3V3 selection capability

This allows the boot configuration of the STM32F401RET6 to be conveniently controlled.

---

## User Interface

The board includes dedicated user indicators and controls.

**User LED**

- D1 — USER_LED
- Controlled through PB0
- R3 = 330 Ω current-limiting resistor

**User Button**

- SW2 — USER_BTN
- Connected to PB1
- R4 = 10 kΩ pull-up resistor

**Power LED**

- D2 — POWER
- R9 = 1 kΩ current-limiting resistor

**USB Status LED**

- D4 — USB_STATUS
- Controlled through PB5
- R12 = 1 kΩ current-limiting resistor

---

## Clock Circuit

The MCU uses an external 8 MHz HSE crystal.

The clock section consists of:

- Y1 — 8 MHz crystal
- C2 — 18 pF
- C3 — 18 pF

The crystal and its load capacitors are placed close to the MCU to maintain a compact and controlled clock path.

---

## Decoupling & Power Integrity

Local decoupling is provided around the STM32F401RET6 and the power-supply circuitry.

The design includes:

- VDD decoupling capacitors
- VCAP capacitor
- Analog supply decoupling
- 3.3 V bulk capacitance
- LDO input and output capacitors

The final PCB placement keeps critical decoupling components close to their respective power pins and maintains short power/ground paths.

---

## PCB Design

The VantageF401RE PCB was designed as a two-layer board while maintaining the competition's maximum board-size requirement.

**Final board dimensions:** 80 mm × 60 mm

**PCB design considerations**

- Central MCU placement
- Short critical signal paths
- Dedicated power section
- USB connector at the board edge
- Accessible programming/debugging header
- Clearly grouped communication headers
- GPIO expansion access
- Local MCU decoupling
- Ground copper zones
- Organized component placement
- Practical connector accessibility
- Compact routing while maintaining design-rule compliance

The PCB layout was independently developed rather than directly reproducing the NUCLEO-F401RE PCB layout.

---

## Final Component Set

The completed design contains 47 populated component references:

| Category | Quantity |
|---|---|
| MCU | 1 |
| USB Protection | 1 |
| Voltage Regulator | 1 |
| Connectors | 8 |
| Crystal | 1 |
| Resistors | 12 |
| Capacitors | 12 |
| LEDs | 3 |
| Diode | 1 |
| Switches | 2 |
| Test Points | 5 |
| **Total** | **47** |

The complete component list is available in:
`bom/VantageF401RE_Final_Component_List.xlsx`

The component reference designators in the final documentation follow the final schematic.

---

## Verification

The design was checked using KiCad's electrical and physical design-rule verification tools.

**ERC — Electrical Rules Check**

- 0 violations
- 0 errors
- 0 warnings

**DRC — Design Rules Check**

- 0 reported DRC errors

The final Gerber and drill files were generated from the completed PCB layout after routing and design-rule verification.

---

## Repository Contents

The repository contains the complete design and supporting documentation.

VantageF401RE/
│
├── bom/
│ ├── VantageF401RE_Final_Component_List.xlsx
│ └── README.md
│
├── docs/
│ ├── Design and supporting documentation
│ ├── Schematic documentation
│ ├── PCB documentation
│ └── Design decision / verification documents
│
├── gerbers/
│ ├── VantageF401RE_Gerbers.zip
│ └── README.md
│
├── kicad/
│ ├── VantageF401RE.kicad_sch
│ ├── VantageF401RE.kicad_pcb
│ └── Supporting KiCad project files
│
├── pdf/
│ ├── VantageF401RE_Final_Design_Report.pdf
│ └── README.md
│
├── results/
│ └── ERC / DRC and validation results
│
└── README.md

---

### Folder Description

**bom/**
Contains the final component list and BOM-related documentation.
`VantageF401RE_Final_Component_List.xlsx` — provides the final component references, values, footprints, functions, and interface mapping.

**docs/**
Contains supporting project documentation, design information, and technical documentation associated with the development of the board.

**gerbers/**
Contains the final manufacturing output package.
`VantageF401RE_Gerbers.zip` — includes the final copper, solder-mask, silkscreen, paste, board-outline, and drill outputs generated from KiCad.

**kicad/**
Contains the primary editable KiCad design files, including:

- Schematic
- PCB layout
- Supporting KiCad project files

These files represent the actual circuit and PCB implementation of VantageF401RE.

**pdf/**
Contains the final technical design report prepared for the competition submission.
`VantageF401RE_Final_Design_Report.pdf` — provides a consolidated description of the board architecture, design decisions, implementation, verification, and final outcome.

**results/**
Contains design verification and validation outputs, including ERC/DRC-related results and other relevant design-check documentation.

---

## Competition Compliance

| Requirement | VantageF401RE |
|---|---|
| STM32F401RE MCU | ✓ |
| Maximum 100 mm × 100 mm | ✓ |
| Exactly 2 copper layers | ✓ |
| Power input | ✓ |
| Voltage regulation | ✓ |
| Decoupling | ✓ |
| Power indication | ✓ |
| SWD interface | ✓ |
| Reset button | ✓ |
| User button | ✓ |
| User LED | ✓ |
| UART | ✓ |
| SPI | ✓ |
| I²C | ✓ |
| GPIO expansion | ✓ |
| USB interface | ✓ |
| ERC verification | ✓ |
| DRC verification | ✓ |
| Gerber generation | ✓ |
| Final BOM | ✓ |
| Technical documentation | ✓ |

---

## Design Philosophy

The VantageF401RE was designed with the following priorities:

- Electrical correctness
- Reliable power distribution
- Practical peripheral access
- Compact PCB organization
- Clear interface grouping
- Debugging accessibility
- Protection and robustness
- Expandability
- Manufacturing-oriented PCB design
- Clean and structured documentation

The design balances the requirements of a development board with the constraints of a compact two-layer PCB.

---

## Final Outcome

The VantageF401RE project progressed from initial architecture and component planning to a completed schematic, PCB layout, verification, and manufacturing-output generation.

The final repository provides the editable KiCad design files together with the final component list, verification results, Gerber package, and technical design report.

The result is a compact, independently developed STM32F401RE evaluation and development board intended to provide convenient access to programming, debugging, communication, GPIO expansion, USB connectivity, and basic user-interface functionality.

---

## Project Information

- **Project:** VantageF401RE
- **Board:** STM32F401RE Evaluation & Development Board
- **Competition:** Mixed Traces PCB Design Competition — 2026
- **Organizer:** Mixed Signals — Electronics Association of MEC
- **Design Tool:** KiCad
- **MCU:** STM32F401RET6
- **PCB:** 2-layer, 80 mm × 60 mm

---

## Acknowledgement

Developed as a submission for the Mixed Traces PCB Design Competition 2026, organized by Mixed Signals — Electronics Association of MEC.
