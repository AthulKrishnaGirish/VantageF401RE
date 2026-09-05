# PCB Placement and Routing Progress

## Placement strategy
- Keep the STM32F401RE near the center of the board.
- Place MCU decoupling capacitors immediately adjacent to their associated supply pins.
- Place the voltage regulator and bulk capacitors close to the power-entry region.
- Place USB at a board edge for mechanical accessibility.
- Keep SWD accessible and clearly labelled.
- Place UART/SPI/I²C/GPIO headers around the board perimeter where practical.
- Keep user controls and LEDs visible and easy to access.
- Reserve a strong ground strategy across both copper layers.

## Routing strategy
- Use short, direct power connections.
- Maintain good ground return paths.
- Avoid unnecessary layer changes on important interfaces.
- Keep USB routing short and appropriately matched/controlled according to the selected implementation.
- Use vias deliberately and keep high-priority signals away from noisy/power-switching areas.
- Use the second copper layer primarily to support grounding and complete difficult signal routes.

## Final validation
The completed PCB will be checked with KiCad DRC and visually reviewed for clearance, silkscreen readability, connector access, routing quality and board-size compliance.
