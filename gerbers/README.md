# VantageF401RE — Gerber Fabrication Files

This folder contains the **final Gerber and drill files** generated from the completed VantageF401RE PCB design for submission to the **Mixed Traces PCB Design Competition** by Mixed Signals, Electronics Association of MEC.

## Gerber Package

**File:** `VantageF401RE_Gerbers.zip`

The ZIP archive contains the manufacturing files required to reproduce the designed 2-layer PCB.

## Included Fabrication Files

The Gerber package contains:

- Front Copper — F.Cu
- Back Copper — B.Cu
- Front Solder Mask — F.Mask
- Back Solder Mask — B.Mask
- Front Silkscreen — F.Silkscreen
- Back Silkscreen — B.Silkscreen
- Front Paste — F.Paste
- Back Paste — B.Paste
- Board Outline — Edge.Cuts
- Excellon Drill File(s)
- Gerber Job File, where applicable

## PCB Specifications

- **Board:** VantageF401RE
- **PCB Type:** 2-layer
- **Board Dimensions:** 80 mm × 60 mm
- **Design Software:** KiCad
- **MCU:** STM32F401RET6

## Verification

The final PCB layout was checked using KiCad's Design Rules Checker (DRC) and completed with **0 reported DRC errors**.

The Gerber files were generated from the final PCB layout after completion of component placement, routing, copper zones, and design-rule verification.

## Fabrication Note

The Gerber ZIP contains the manufacturing outputs of the VantageF401RE PCB design. These files are provided for competition submission and fabrication reference.

The PCB has **not been physically fabricated or hardware-tested** as part of this design submission.
