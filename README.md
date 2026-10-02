# EEE208-7segment-decoder
Analog voltage (0–9 V) to 7-segment decimal display decoder with no decoder IC. Uses a resistor ladder, UA741 comparators, zener level shifters, BC547 inverters and 1N4148 diode logic. Simulated in PSpice 9.2. EEE 208 Group 16, BUET.
# Voltage-Based 0–9 Decimal to 7-Segment Display Decoder (PSpice)

**EEE 208 – Electronic Circuits II Laboratory, BUET (January 2026)**
Section A1, Group 16

**Members**
- Md Abu Basir (2306031)
- Md Sabbir Hossain (2306032)

## Overview
This project converts a DC input voltage between 0 V and 9 V into the matching decimal digit (0–9) on a 7-segment display, without using a dedicated decoder IC. The circuit was designed and simulated in PSpice Student Version 9.2.

## How it works
1. **Reference ladder** – a resistor chain generates nine thresholds: 0.5 V, 1.5 V, …, 8.5 V.
2. **Comparator bank** – nine UA741 op-amps compare Vin with each threshold.
3. **Level shifters** – 1N750 diode-clamped voltage dividers reduce the ±11.81 V comparator outputs to about 4.6 V (HIGH) and −0.7 V (LOW).
4. **Inverters** – BC547 transistors produce the complementary signals.
5. **Digit lines (D0–D9)** – 1N4148 diode AND gates select exactly one digit line.
6. **Diode segment matrix** – a diode OR matrix drives segments a–g.
7. **7-segment display** – a segment at about 5 V is ON, and a segment in the millivolt range is OFF.

## Results
For every input from 0 V to 9 V, the correct segments turned ON (about 5 V) and the others stayed below about 0.62 V.

## Components
UA741 ×9, BC547 ×9, 1N4148 ×65, 1N750 ×9, resistors (about 50), 7-segment display ×1.

## How to run
1. Open the project file (`.opj`) in PSpice 9.2.
2. Set the source **Vin** to a value from 0 V to 9 V.
3. Run the simulation.
4. Read the voltages at the segment nodes a–g (about 5 V = ON).

## Repository contents
- `PSpice/` – schematic and simulation files
- `images/` – circuit and output screenshots
- `Report/` – final project report
- `Presentation/` – final presentation slides

## Note
This is a simulation-only project. A real display would need transistor drivers and current-limiting resistors.
