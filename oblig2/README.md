# Assignment 2 — Voltage Dividers and Analog Measurements

Exploring Ohm’s law, voltage dividers and electrical loading through Python calculations and practical Arduino experiments.

Completed for **IN1080: Mechatronics**, University of Oslo.

**Author:** Frida Berge (`fridatbe`)  
**Report date:** February 22, 2023

## Overview

This assignment combines theoretical circuit analysis with breadboard experiments:

- Plotting current as a function of voltage.
- Calculating and plotting voltage-divider outputs.
- Comparing calculated and measured voltages.
- Reading a variable voltage through Arduino’s analog input.
- Observing how an external load affects a high-resistance voltage divider.

See [taskdescription.md](./taskdescription.md) for the assignment requirements.

## Tools and Components

### Software

- Python with NumPy and Matplotlib.
- Arduino IDE.
- Arduino Serial Monitor or Serial Plotter.

### Hardware

- Arduino with a 5 V supply and analog input A0.
- Breadboard and jumper wires.
- Multimeter.
- Resistors.
- Potentiometer.
- LED.

The final experiment specifies two 10 MΩ resistors.

## Experiments and Recorded Results

### 1. Current through a resistor

A Python script plots current through a 100 Ω resistor as the applied voltage increases.

The calculation uses Ohm’s law:

\[
I = \frac{V}{R}
\]

The implementation uses `np.arange(1, 10, 0.1)`, so the plotted range starts at 1 V and stops just below 10 V.

### 2. Calculating a voltage divider

For a 10 V supply, a 150 Ω upper resistor and a desired output of 2.5 V across the lower resistor:

\[
V_{\mathrm{out}} = V_{\mathrm{in}}
\frac{R_1}{R_1 + R_2}
\]

Solving for the lower resistor gives:

\[
R_1 = 50\,\Omega
\]

### 3. Variable-resistance simulation

A second Python script plots the voltage across the lower resistor as its resistance varies from 1 Ω to just below 1,000 Ω.

The supply remains at 10 V and the upper resistor at 150 Ω.

### 4. Physical voltage divider

The assignment specified a 4.7 kΩ lower resistor and a 10 kΩ upper resistor. The report records substituting a **16 kΩ resistor** for the upper resistor.

| Quantity | Recorded value |
| --- | ---: |
| Supply voltage | 5 V |
| Lower resistor | 4.7 kΩ |
| Upper resistor, reported substitution | 16 kΩ |
| Calculated output, rounded | 1.1 V |
| Measured output | 1.6 V |

The report discusses measurement uncertainty and non-ideal components as possible explanations for the difference.

**Interpretation note:** the measured 1.6 V is also close to the theoretical output for the originally specified 10 kΩ upper resistor. The report does not establish the cause of the discrepancy; checking the installed resistance values and wiring would help resolve it.

### 5. Potentiometer and LED

A voltage divider with a potentiometer is connected to Arduino input A0, with an LED connected across the potentiometer.

The report records:

- Analog readings varying from **0 to 536**.
- The LED switching on and off as the potentiometer was adjusted.

These values are reported as raw analog readings, not voltages in volts.

### 6. Loading a high-resistance divider

The final task investigates a divider with two 10 MΩ resistors.

The report records a substantial reduction in the measured output, reaching zero, when a load was introduced through finger contact between the output and ground.

This is a qualitative observation rather than a calibrated measurement of body resistance or loading.

## Running the Code

### Python plots

Install the dependencies:

```bash
python -m pip install numpy matplotlib
```

Run the Python scripts for Tasks 1 and 3 from this folder. The code reproduced in the report saves plots as `opg1.png` and `opg2.png`.

### Arduino experiment

1. Assemble the circuit for the relevant task.
2. Open the Arduino sketch in Arduino IDE.
3. Select the connected board and port.
4. Upload the sketch.
5. Open Serial Monitor or Serial Plotter.
6. Match the serial baud rate to the value configured in the sketch.

Task 5 requests five readings per second. Check the sketch for its actual sampling delay and serial configuration.

## Scope and Limitations

- Results are taken from the original report and have not been independently reproduced.
- The resistor substitution and measured voltage in Task 4 remain inconsistent.
- Tasks 5 and 6 provide qualitative observations rather than repeated measurements with uncertainty estimates.
- The report’s extracted text does not establish the exact Arduino sketch contents or serial configuration.

## Attribution

The circuit exercises and experimental requirements were supplied by the course.

My submission contains the Python plotting code, voltage-divider calculations, recorded measurements and observations from the practical experiments.
