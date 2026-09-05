# VantageF401RE

### STM32F401RE Evaluation & Development Board

**Mixed Traces PCB Design Competition — 2026**

VantageF401RE is an independently designed, compact two-layer STM32F401RE-based evaluation and development board developed using KiCad.

The project aims to satisfy all mandatory competition requirements while improving usability, expandability, organization, power distribution and overall PCB design quality.

## Project Status

**Current stage:** Initial architecture and design planning

The STM32F401RET6 (STM32F401RE family, LQFP-64) has been selected as the main MCU. The system architecture, required interfaces, preliminary component selection and PCB placement/routing strategy have been established. Schematic implementation and electrical validation are the next development milestones.

## Planned Features

### Core
- STM32F401RET6 MCU (STM32F401RE family, LQFP-64)
- 3.3 V regulated power supply
- MCU power decoupling
- Reset and boot configuration
- Power indication

### Programming & Debugging
- SWD interface
- SWDIO
- SWCLK
- NRST
- VCC
- GND

### Communication
- USB
- UART
- SPI
- I²C

### User Interface
- Reset button
- User button
- User LED
- Power LED

### Expansion
- GPIO headers
- 3.3 V and GND access
- Dedicated communication-interface access

## Design Constraints

| Parameter | Requirement |
|---|---|
| MCU | STM32F401RET6 |
| PCB layers | Exactly 2 copper layers |
| Maximum board size | 100 mm × 100 mm |
| Design software | KiCad |
| Fabrication | Not required |
| Reference | STM32 NUCLEO-F401RE / MB1136 |

## Design Approach

The STM32 NUCLEO-F401RE is being used as a functional and architectural reference. The VantageF401RE schematic, component arrangement and PCB routing will be independently developed rather than directly copying the NUCLEO PCB layout.

The design prioritizes:

- Electrical correctness
- Power integrity
- Compact PCB organization
- Accessible connectors
- Clear silkscreen
- Expandability
- Cost optimization
- High-quality two-layer routing

## Repository Structure

```text
VantageF401RE/
│
├── docs/
│   ├── VantageF401RE_Progress_Evaluation_Report.docx
│   ├── VantageF401RE_Block_Diagram.png
│   ├── Schematic_Progress.md
│   ├── PCB_Placement_Routing_Progress.md
│   └── Major_Design_Decisions.md
│
├── bom/
│   └── VantageF401RE_Initial_Component_Selection.xlsx
│
├── kicad/
│   └── KiCad project files
│
└── results/
    └── ERC / DRC and final validation results
```

## Development Roadmap

```text
Architecture
     ↓
MCU Pin Allocation
     ↓
Component Selection
     ↓
Schematic
     ↓
ERC
     ↓
Footprint Verification
     ↓
PCB Placement
     ↓
2-Layer Routing
     ↓
Ground Plane
     ↓
DRC
     ↓
Optimization
     ↓
BOM & Cost Analysis
     ↓
Documentation
     ↓
Final Submission
```

## Team Meta Man

**Project:** VantageF401RE  
**Competition:** Mixed Traces PCB Design Competition  
**Organization:** Mixed Signals — Electronics Association of MEC
