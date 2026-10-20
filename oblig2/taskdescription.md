# Assignment 2 — Task Description

**Course:** IN1080 — Mechatronics  
**Source:** Course assignment text supplied with this repository’s documentation.

This document is an English summary of the original Norwegian assignment. It describes the requirements, not the completed results.

## Objective

Investigate Ohm’s law, voltage dividers, analog measurements and the effect of loading through calculations, Python or MATLAB plots, and Arduino experiments.

## Task 1 — Current as a Function of Voltage

Use Python or MATLAB to plot the current through a **100 Ω resistor**.

- Vary the voltage from **1 V to 10 V**.
- Use increments of **0.1 V**.
- Plot current as a function of voltage.

## Task 2 — Calculate a Voltage Divider

Determine the value of the lower resistor, R1, required to obtain an output voltage of **2.5 V across R1**.

Use:

- Supply voltage: **10 V**.
- Upper resistor, R2: **150 Ω**.

Include the calculation in the report.

The component values are taken from the accompanying solution because the circuit illustration is not reproduced here.

## Task 3 — Plot a Voltage Divider

Using the circuit from Task 2:

- Vary R1 from **1 Ω to 1,000 Ω**.
- Plot the voltage across R1 as a function of its resistance.
- Keep the supply voltage and R2 unchanged.

## Task 4 — Build and Measure a Voltage Divider

### Components

| Component | Designation |
| --- | --- |
| 4.7 kΩ resistor | R1 |
| 10 kΩ resistor | R2 |
| Multimeter | M1 |

Build the circuit on a breadboard:

- Connect the 10 kΩ resistor between Arduino’s **5 V supply** and the output node.
- Connect the 4.7 kΩ resistor between the output node and **GND**.

Then:

1. Calculate the theoretical voltage across the 4.7 kΩ resistor.
2. Measure the voltage with a multimeter.
3. Include both the calculation and measurement in the report.
4. Discuss possible causes of any difference.

Use resistor colour codes to check component values.

## Task 5 — Potentiometer and Analog Readings

### Components

| Component | Designation |
| --- | --- |
| 4.7 kΩ resistor | R1 |
| Potentiometer | P1 |
| LED | LED1 |

Build a voltage divider between **5 V** and **GND** using the fixed resistor and potentiometer.

- Connect the output node between the two resistive elements.
- Connect the LED between the output and GND, in parallel with the potentiometer.
- Connect the output to Arduino input **A0**.
- Wire the potentiometer so that adjusting it changes its resistance.

Write an Arduino sketch that:

1. Reads A0 using `analogRead()`.
2. Sends the reading to the computer using `Serial.println()`.
3. Repeats this **five times per second**.

A delay may be used to control the sampling interval.

Inspect the readings using Arduino IDE’s **Serial Plotter** or **Serial Monitor**. Include a screenshot of the plot in the report.

Observe how adjusting the potentiometer affects the readings and LED.

## Task 6 — Loading and Noise

### Components

| Component | Designation |
| --- | --- |
| 10 MΩ resistor | R1 |
| 10 MΩ resistor | R2 |

Remove the LED and replace the previous divider’s resistor and potentiometer with two **10 MΩ resistors**.

The original instructions state that these resistors are available from course staff or the IFI reception rather than the standard kit.

### Loading experiment

While using only the assignment’s low-voltage Arduino circuit:

- Touch the divider output with one finger.
- Touch GND with another finger.
- Observe whether the measured output changes.

The experiment investigates the effect of adding a high-resistance load between the output and ground.

### Noise observation

Observe fluctuations in the readings from the high-impedance output, including changes associated with touching the circuit.

Include a screenshot of the plot in the report.

## Required Submission

Replace `<username>` with the student’s username.

| Deliverable | Required filename |
| --- | --- |
| Task 1 Python or MATLAB code | `oblig2_1_<username>.py` or `oblig2_1_<username>.m` |
| Task 3 Python or MATLAB code | `oblig2_3_<username>.py` or `oblig2_3_<username>.m` |
| Task 5 Arduino sketch | `oblig2_<username>.ino` |
| Written report with illustrations | `oblig2_<username>.pdf` |

The report should include calculations, measurements, observations and the requested screenshots.

## General Requirements

- Follow the laboratory safety procedures.
- Follow IFI’s rules for compulsory assignments.
- Complete the assignment individually unless otherwise stated.
- Submit the required files through Canvas.
- Include a title and axis labels on every plot.
- Include units in parentheses for physical quantities.
- Use a legend when displaying multiple curves.

## Attribution

The original assignment was provided by the University of Oslo for IN1080. This document translates and condenses the supplied task text; it does not reproduce the original circuit illustrations.
