# VantageF401RE — Final Design Report

This folder contains the **final drafted design report** prepared for the **Mixed Traces PCB Design Competition** by Mixed Signals, Electronics Association of MEC.

## Final Report

**File:** `VantageF401RE_Final_Design_Report.pdf`

The report documents the completed design and development of the **VantageF401RE**, a custom 2-layer STM32F401RE-based evaluation and development board designed in KiCad.

## Contents of the Report

The final report includes:

- Project overview and objectives
- Problem statement and proposed solution
- System architecture and functional block diagram
- STM32F401RET6 microcontroller selection
- Power supply and 3.3 V regulation
- USB-C power and USB 2.0 interface
- USB ESD protection
- SWD programming and debugging interface
- UART, SPI, and I²C interfaces
- GPIO expansion
- Reset and BOOT selection circuitry
- User button and LED indicators
- External 5 V input and protection
- Crystal oscillator and clock circuitry
- MCU decoupling and power integrity considerations
- PCB component placement and routing
- 2-layer PCB design
- Design considerations and major design decisions
- ERC and DRC verification
- Final board specifications
- Bill of Materials overview
- Final design outcome and conclusion

## Final Board Specifications

- **MCU:** STM32F401RET6
- **PCB Layers:** 2 copper layers
- **PCB Size:** 80 mm × 60 mm
- **Design Tool:** KiCad
- **USB Interface:** USB Type-C, USB 2.0
- **Debug Interface:** SWD
- **Communication Interfaces:** UART, SPI, I²C
- **Expansion:** 20-pin GPIO header
- **Power:** USB-C 5 V input / external 5 V input
- **Logic Supply:** 3.3 V
- **Verification:** ERC completed with 0 violations; DRC completed with 0 reported errors

## Note

This report represents the **final PCB design and documentation** prepared for competition submission. The design was completed and verified in KiCad. No physical fabrication or hardware testing is claimed unless explicitly stated in the report.

For the authoritative circuit implementation and component reference designators, refer to the final KiCad schematic and PCB files in the repository.
