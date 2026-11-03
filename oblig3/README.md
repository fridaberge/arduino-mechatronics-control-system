# Assignment 3 — Circuit Analysis and RC Low-Pass Filters

Theoretical circuit analysis and practical frequency-response measurements for **IN1080: Mechatronics**, University of Oslo.

**Author:** Frida Berge (`fridatbe`)  
**Report date:** March 7, 2023

## Overview

This assignment explores:

- Kirchhoff’s current law.
- Kirchhoff’s voltage law.
- Superposition of independent sources.
- Thévenin equivalent circuits.
- The cutoff frequency and phase response of an RC low-pass filter.

Tasks 1–3 involve analytical calculations. Task 4 compares the theoretical response of a low-pass filter with measurements made using Analog Discovery 2.

## Report

My answers to the tasks—including calculations, measurements, screenshots and reflections—are documented in [oblig3_fridatbe.pdf](./oblig3_fridatbe.pdf).

For the original assignment instructions and circuit diagrams, see [taskdescription.pdf](./taskdescription.pdf).

## Folder Structure

```text
oblig3/
├── README.md
├── taskdescription.pdf
├── oblig3_fridatbe.pdf
└── media/
    ├── README.md
    └── Pictures, screenshots and illustrations
```

| Location | Contents |
| --- | --- |
| [Report](./oblig3_fridatbe.pdf) | My answers, calculations, measurements and reflections |
| [Task description](./taskdescription.pdf) | Original instructions and circuit diagrams |
| [media/](./media/) | Pictures, screenshots and illustrations |

## Tasks and Results

### 1. Kirchhoff’s Current Law

Determine the current through a 40 Ω resistor in a circuit containing:

- A 5 V voltage source.
- A 2 mA current source.
- A 20 Ω resistor.
- A 40 Ω resistor.

My solution uses Kirchhoff’s current law and superposition to calculate the contributions from the two sources.

The report gives a combined current of **83.67 mA**. This uses rounded intermediate values; using the exact component values gives **84 mA**.

### 2. Kirchhoff’s Voltage Law

Determine the voltage across a 40 Ω resistor in a series circuit with opposing 12 V and 6 V sources.

The circuit contains resistors of 20 Ω, 40 Ω, 10 Ω and 20 Ω.

The report calculates a voltage of approximately **2.67 V** across the 40 Ω resistor and checks the result using Kirchhoff’s voltage law.

### 3. Thévenin Equivalent

Find the equivalent circuit seen at the output terminals of a network containing:

- A 5 V voltage source.
- A 100 mA current source.
- Two 20 Ω resistors.

The reported equivalent is:

| Quantity | Result |
| --- | ---: |
| Thévenin voltage | 3.5 V |
| Thévenin resistance | 10 Ω |

### 4. RC Low-Pass Filter

Build a low-pass filter using a **1 kΩ resistor** and a **1 µF capacitor**.

Use Analog Discovery 2 and the WaveForms Network Analyzer to measure the magnitude and phase response, with the output taken across the capacitor.

| Quantity | Theoretical | Reported measurement |
| --- | ---: | ---: |
| Cutoff frequency | 159.15 Hz | 140.13 Hz |
| Phase-lag magnitude near cutoff | 45° | 42.64° |

The phase values above are magnitudes of the lag; the filter output lags the input.

The report discusses the lower measured cutoff frequency and phase-lag magnitude, noting that the measurement marker may not have been positioned exactly at the −3 dB point.

## Equipment and Software

- Breadboard and jumper wires.
- 1 kΩ resistor.
- 1 µF capacitor.
- Analog Discovery 2.
- WaveForms Network Analyzer.

## Reproducing the Filter Measurement

1. Connect the resistor and capacitor in series on the breadboard.
2. Connect waveform generator W1 and oscilloscope channel 1 to the resistor’s input.
3. Connect oscilloscope channel 2 to the junction between the resistor and capacitor.
4. Connect the capacitor’s other terminal and both oscilloscope reference leads to ground.
5. Open the WaveForms Network Analyzer.
6. Configure the frequency sweep from 10 Hz to 100 kHz.
7. Display magnitude and phase, then use a marker to inspect the response near −3 dB.

Refer to the task-description PDF for the original wiring illustration and display settings. Follow the course’s laboratory safety procedures.

## Notes

The PDF preserves my original submission. Results summarized here are taken from that report and have not been independently reproduced.

The assignment’s required deliverable was a written PDF report with a measurement screenshot; source code was not explicitly required.

## Attribution

The assignment instructions and supplied circuit diagrams were provided by the course.

My contribution consists of the circuit calculations, recorded filter measurements and discussion presented in the report.
