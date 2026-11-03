# Code — Assignment 4

Source code supporting **IN1080: Mechatronics**, Assignment 4: LED driver analysis and Arduino traffic-light control.

## Python — LED Analysis

The report includes Python code for:

- Plotting LED current as a function of voltage.
- Calculating current at 1.14 V for ideality factors of 1.6 and 1.3.
- Iteratively estimating the current with a 10 V supply and a 9 Ω series resistor.

### Dependencies

The plotting code shown in the report uses:

- Python 3.
- NumPy.
- Matplotlib.
- Python’s built-in `math` module.

Install the external packages with:

    python -m pip install numpy matplotlib

Run the relevant Python file from this folder. Check its contents for output filenames and whether it saves or displays the plot.

### Reported Results

| Calculation | Result |
| --- | ---: |
| Current at 1.14 V, ideality factor 1.6 | Approximately 0.93 A |
| Current at 1.14 V, ideality factor 1.3 | Approximately 537 A |
| Current with 9 Ω resistor, ideality factor 1.6 | Approximately 0.984 A |
| Current with 9 Ω resistor, ideality factor 1.3 | Approximately 1.007 A |

These are simplified model calculations, not measured hardware currents.

## Arduino — Traffic-Light Control

The traffic-light exercise uses vehicle and pedestrian LEDs, a request button, a blue acknowledgement LED and a piezo sounder.

### Required Pin Mapping

| Pin | Function |
| --- | --- |
| D2 | Request button |
| D3 | Blue acknowledgement LED |
| D4 | Pedestrian green LED |
| D5 | Pedestrian red LED |
| D10 | Piezo sounder |
| D11 | Vehicle green LED |
| D12 | Vehicle yellow LED |
| D13 | Vehicle red LED |

### Assignment Requirements

- Non-blocking timing for the light and sound sequences.
- Interrupt-based handling of the request button.
- Acknowledgement of a pending request using the blue LED.
- Different audible signal intervals during idle and pedestrian crossing.
- Three green flashing cycles before the pedestrian light returns to red.

Consult the sketch to verify how these requirements are implemented.

### Uploading the Sketch

1. Assemble the circuit according to the report and task description.
2. Use a 220 Ω series resistor for each LED and a 10 kΩ pull-down resistor for the button.
3. Open the `.ino` sketch in Arduino IDE.
4. Select **Arduino Uno** and the correct serial port.
5. Compile and upload the sketch.
6. Test the idle state, button acknowledgement and complete crossing sequence.

Arduino IDE may require the `.ino` file to be stored in a folder with the same name as the sketch.

Disconnect power before modifying the circuit.

## Related Documentation

- [Assignment overview](../README.md)
- [Original task description](../taskdescription.pdf)
- [My report](../oblig4_fridatbe.pdf)
- [LaTeX report source](../oblig4_fridatbe.tex)
- [Supporting media](../media/)
