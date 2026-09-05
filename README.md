# VantageF401RE

STM32F401RE two-layer evaluation/development board for the Mixed Traces PCB Design Competition.

## Project status
**Progress-review stage:** architecture and design planning established; schematic and PCB implementation are the next engineering milestones.

## Core requirements
- STM32F401RE / STM32F401RET6
- Exactly 2 copper layers
- Maximum 100 mm × 100 mm
- KiCad
- SWD
- Power regulation and decoupling
- Reset button
- User button
- User LED
- Power LED
- UART, SPI, I²C
- GPIO/power/ground expansion
- USB communication
- Schematic, PCB, BOM, documentation, ERC and DRC for final submission

## Design philosophy
VantageF401RE is intended to meet all mandatory requirements while improving connector accessibility, expansion capability, layout organization, serviceability and cost effectiveness. The NUCLEO-F401RE is used as a functional reference; the submitted PCB layout will be independently designed.

## Repository structure
```text
VantageF401RE/
├── README.md
├── docs/
│   ├── VantageF401RE_Progress_Evaluation_Report.docx
│   ├── VantageF401RE_Block_Diagram.png
│   ├── Schematic_Progress.md
│   ├── PCB_Placement_Routing_Progress.md
│   └── Major_Design_Decisions.md
├── bom/
│   └── VantageF401RE_Initial_Component_Selection.xlsx
├── kicad/
│   └── README.md
└── results/
    └── README.md
```

## Note
This is an engineering progress repository. Files are updated as the design advances from architecture to schematic, PCB layout, ERC/DRC and final documentation.
