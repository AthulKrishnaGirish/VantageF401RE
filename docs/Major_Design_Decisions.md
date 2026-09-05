# Major Design Decisions

1. **MCU:** STM32F401RET6 in the LQFP-64 package has been selected as the main microcontroller.

2. **Board purpose:** The board is being developed as a general-purpose STM32 evaluation and development platform rather than a minimal MCU breakout.

3. **PCB layers:** The design will use exactly two copper layers as specified by the competition.

4. **Board size:** The board will remain within the 100 mm × 100 mm maximum size, with the final dimensions chosen based on component placement and routing requirements.

5. **Programming and debugging:** A dedicated SWD interface will be provided for programming and debugging. An onboard ST-Link section will not be included.

6. **Communication:** USB, UART, SPI and I²C interfaces will be provided.

7. **Expansion:** GPIO, power and ground connections will be exposed through clearly labelled headers for external modules and experiments.

8. **Power integrity:** Local decoupling and organized power distribution will be given high priority during schematic and PCB development.

9. **Usability:** Connectors, buttons, LEDs and major functional sections will be positioned and labelled for easy identification and access.

10. **Originality:** The NUCLEO-F401RE will be used as a functional reference, while the VantageF401RE schematic organization, component placement and PCB routing will be independently developed.

11. **Optimization:** Additional features will be considered based on their usefulness, cost, board area and routing impact rather than adding unnecessary components.

12. **Design objective:** The final board will aim to combine electrical correctness, compact layout, expandability, usability, cost efficiency and professional PCB organization.
