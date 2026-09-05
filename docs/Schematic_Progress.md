# Schematic Progress

The VantageF401RE schematic is being structured into the following functional blocks:

1. Power input and 3.3 V regulation
2. STM32F401RE MCU core
3. MCU decoupling and power integrity
4. Reset and boot configuration
5. SWD programming/debug interface
6. USB communication interface
7. UART interface
8. SPI interface
9. I²C interface
10. GPIO/power/ground expansion
11. User button and user LED
12. Power indication

## Design checks planned
- Correct MCU power-pin connectivity
- Correct ground connectivity
- Decoupling placement and values
- NRST and BOOT0 handling
- SWD signal and supply connections
- USB signal/power connectivity
- Interface pin allocation
- ERC cleanup

## Next milestone
Complete the KiCad schematic and run ERC before beginning final PCB placement.
