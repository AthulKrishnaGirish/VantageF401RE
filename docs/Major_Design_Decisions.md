# Major Design Decisions

1. **MCU:** STM32F401RE / STM32F401RET6 as required.
2. **Board architecture:** evaluation/development board rather than a minimal MCU breakout.
3. **Layers:** exactly two copper layers.
4. **Size:** remain comfortably below the 100 mm × 100 mm maximum rather than targeting the limit unnecessarily.
5. **Debugging:** SWD header included; on-board ST-Link omitted as permitted.
6. **Interfaces:** USB, UART, SPI and I²C included.
7. **Expansion:** dedicated GPIO/power/ground headers planned.
8. **Usability:** clear silkscreen, labelled connectors and accessible user controls.
9. **Power integrity:** local MCU decoupling and organized power distribution are design priorities.
10. **Originality:** component placement and routing will be independently developed instead of reproducing the NUCLEO PCB layout.
11. **Competitive direction:** evaluate useful enhancements only when they improve functionality without creating unnecessary schematic/routing complexity.
