# Major Design Decisions

The following decisions guided the development of the **VantageF401RE** STM32F401RE-based evaluation and development board.

## 1. MCU Selection

**STM32F401RET6** in the **LQFP-64** package was selected as the main microcontroller.

The device provides sufficient processing capability, memory, GPIO availability, and peripheral interfaces for the intended evaluation and development applications.

## 2. Board Purpose

The VantageF401RE was designed as a **general-purpose STM32 evaluation and development platform**, rather than a minimal MCU breakout board.

The design therefore integrates power management, USB connectivity, debugging, communication interfaces, GPIO expansion, user controls, indicators, and test access on a single board.

## 3. PCB Layer Constraint

The PCB uses **exactly two copper layers**, in accordance with the competition requirements.

The placement and routing strategy was developed with the limitations of a 2-layer design in mind, while maintaining practical signal and ground connectivity.

## 4. Board Size

The final PCB dimensions were selected as **80 mm × 60 mm**, remaining comfortably within the competition's maximum permitted **100 mm × 100 mm** board area.

The dimensions were chosen to provide sufficient space for the required interfaces and supporting circuitry while maintaining a compact development-board form factor.

## 5. Programming and Debugging

A dedicated **5-pin SWD interface** was implemented for programming and debugging the STM32.

The SWD interface provides:

- VCC
- SWDIO
- GND
- SWCLK
- NRST

An onboard ST-Link programmer/debugger was intentionally not included, allowing the board to remain simpler and more compact while supporting external SWD programmers/debuggers.

## 6. USB Interface

A **USB Type-C interface** was implemented to provide USB 2.0 connectivity and 5 V power input.

The USB section includes:

- USB D+ and D− connections
- CC1 and CC2 resistors
- Dedicated USB ESD protection
- USB data-line series resistors
- USB 5 V power rail
- USB status indication

The USB interface was designed as both a functional communication interface and a convenient primary power source for the board.

## 7. Power Architecture

A dedicated **AP2112K-3.3 LDO regulator** was selected to generate the regulated 3.3 V supply required by the STM32 and associated circuitry.

The power architecture supports:

- USB-C 5 V input
- External 5 V input
- Schottky-diode protection on the external 5 V path
- 3.3 V regulation
- Regulator input and output decoupling
- MCU power decoupling
- Analog supply decoupling
- Power indication

This provides a practical and protected power system while keeping the circuitry compact.

## 8. Communication Interfaces

Dedicated headers were provided for commonly used embedded communication protocols:

- **UART**
- **SPI**
- **I²C**

These interfaces were exposed with appropriate power and ground connections to simplify connection to external modules and peripherals.

## 9. GPIO Expansion

A dedicated **2×10 GPIO header** was included to expose multiple STM32 GPIOs along with power and ground connections.

The expansion interface was designed to support external sensors, displays, modules, and other experimental circuits without requiring modification to the main PCB.

## 10. Reset and Boot Configuration

Dedicated hardware controls were implemented for reliable startup and development.

The design includes:

- Hardware reset push button
- NRST pull-up resistor
- BOOT0 pull-down resistor
- BOOT selection header

This provides convenient control over reset and boot-mode selection during development and debugging.

## 11. User Interface and Indicators

The board includes dedicated visual and user-control elements:

- User push button
- User LED
- Reset button
- Power LED
- USB status LED

These features provide immediate feedback and improve usability during firmware development and hardware testing.

## 12. Clock and Decoupling Strategy

An external **8 MHz crystal oscillator** was selected for the MCU clock source.

The crystal and its load capacitors were placed close to the corresponding MCU pins.

The design also incorporates local power decoupling, including:

- 100 nF MCU decoupling capacitors
- 4.7 µF bulk decoupling
- Analog supply decoupling
- VCAP1 capacitor
- Regulator input/output capacitors

The placement strategy prioritizes short connections between supply pins and their associated decoupling components.

## 13. Protection and Reliability

Protection features were included where they provide practical benefit without unnecessarily increasing board complexity.

The USB interface uses dedicated **ESD protection**, while the external 5 V input incorporates a Schottky-diode protection path.

Power filtering and local decoupling were also incorporated to improve supply stability and reduce the impact of transient disturbances.

## 14. Test and Debug Accessibility

Dedicated test points were included for important signals:

- 3.3 V
- GND
- SWDIO
- SWCLK
- NRST

These provide convenient access for debugging, probing, waveform measurement, and laboratory testing.

## 15. PCB Organization and Placement

The PCB was organized into functional regions to improve accessibility and simplify routing.

Major sections include:

- STM32 MCU core
- USB interface
- Power regulation
- SWD/debug interface
- Communication interfaces
- GPIO expansion
- Clock circuitry
- User controls and indicators
- Test points

Components were positioned with consideration for signal paths, accessibility, power distribution, and the constraints of a two-layer PCB.

## 16. Ground and Power Integrity

Power integrity was treated as an important part of the PCB design.

The design uses:

- Local decoupling
- Dedicated bulk capacitors
- Analog supply filtering
- Organized power distribution
- Ground planes
- Short connections around critical power components

The routing strategy was developed to provide practical return-current paths while maintaining clean functional organization.

## 17. Originality

The **NUCLEO-F401RE** was used as a functional and architectural reference for understanding the STM32F401RE platform and its development-board requirements.

However, the VantageF401RE schematic organization, component selection, functional additions, component placement, board dimensions, and PCB routing were independently developed.

The final PCB is therefore a custom implementation rather than a direct reproduction of the NUCLEO-F401RE layout.

## 18. Feature Selection and Optimization

Additional features were selected based on their practical usefulness, available board area, routing complexity, component count, and overall design value.

Rather than adding features solely for complexity, the design prioritizes features that improve the board's usefulness as an evaluation and development platform.

## 19. Verification

The completed design was validated using KiCad's electrical and PCB design-rule checking tools.

The final results were:

- **ERC: 0 violations**
- **DRC: 0 reported violations**
- **4 intentional DRC exclusions**, corresponding to reviewed USB-C connector mechanical clearance checks

The detailed verification reports are available in the `results/` directory.

## 20. Final Design Objective

The final VantageF401RE design combines:

**Functionality + Expandability + Protection + Debug Accessibility + Power Management + Compact 2-Layer Design + Verification**

The overall objective was to create a practical and professionally organized STM32 development platform that satisfies the competition requirements while providing useful features for real-world embedded-system experimentation.
