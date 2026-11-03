# Code — Assignment 4

Source code and circuit-design files for **IN1080: Mechatronics**, Assignment 4.

The Python scripts answer Tasks 1 and 5 of the LED-driver exercise. The Arduino sketch solves the traffic-light task.

## Files

| File | Purpose |
| --- | --- |
| [oblig4_1.py](./oblig4_1.py) | Task 1: LED current–voltage plot and current calculation |
| [oblig4_5.py](./oblig4_5.py) | Task 5: Numerical current calculation with a series resistor |
| [trafikklys.ino](./trafikklys.ino) | Arduino traffic-light controller |
| [Draft1.asc](./Draft1.asc) | LTspice schematic file |
| [Draft2.asc](./Draft2.asc) | LTspice schematic file |

## Task 1 — LED Current–Voltage Analysis

**File:** [oblig4_1.py](./oblig4_1.py)

Plots the LED current as a function of voltage using the diode model provided in the assignment.

The task uses an ideality factor of 1.6 and asks for:

- A voltage range from 0 to 1.4 V.
- A displayed current range from 0 to 2 A.
- The calculated current at a supply voltage of 1.14 V.

The code excerpt in the report also calculates the current for an ideality factor of 1.3, supporting Task 2.

### Reported Results

| Ideality factor | Calculated current at 1.14 V |
| --- | ---: |
| 1.6 | Approximately 0.93 A |
| 1.3 | Approximately 537 A |

These values come from the simplified mathematical model. They are not measured currents or safe operating recommendations.

## Task 5 — Current With a Series Resistor

**File:** [oblig4_5.py](./oblig4_5.py)

Numerically estimates the LED current using:

- A 10 V supply.
- A 9 Ω series resistor, calculated in Task 4.
- LED ideality factors of 1.6 and 1.3.

The calculation iteratively adjusts the diode voltage to satisfy the circuit’s voltage relationship.

### Reported Results

| Ideality factor | Calculated current |
| --- | ---: |
| 1.6 | Approximately 0.984 A |
| 1.3 | Approximately 1.007 A |

The results illustrate how a series resistor reduces the sensitivity of the current to changes in the LED model.

## Running the Python Scripts

The Python code shown in the report uses Python 3, NumPy, Matplotlib and the built-in `math` module.

Install the external dependencies:

```bash
python -m pip install numpy matplotlib
```

Run the scripts from this folder:

```bash
python oblig4_1.py
python oblig4_5.py
```

The Task 1 code shown in the report saves its plot as `opg1.png`. The calculated currents are printed to the terminal.

## Traffic-Light Controller

**File:** [trafikklys.ino](./trafikklys.ino)

Arduino sketch for the pedestrian-crossing task. The system uses vehicle lights, pedestrian lights, a request button, a blue acknowledgement LED and a piezo sounder.

### Pin Mapping

| Arduino pin | Component | Function |
| --- | --- | --- |
| D2 | Pushbutton | Pedestrian crossing request |
| D3 | Blue LED | Request acknowledgement |
| D4 | Green LED | Pedestrian green |
| D5 | Red LED | Pedestrian red |
| D10 | Piezo sounder | Audible signal |
| D11 | Green LED | Vehicle green |
| D12 | Yellow LED | Vehicle yellow |
| D13 | Red LED | Vehicle red |

### Task Requirements

The assignment specifies the following sequence:

1. Vehicles have green and pedestrians have red while no crossing request is pending.
2. A button press is acknowledged by the blue LED.
3. After 2 seconds, vehicles receive yellow, followed by red 1 second later.
4. After another 1 second, pedestrians receive green.
5. Pedestrian green remains on for 6 seconds, then flashes for three cycles before returning to red.
6. Once pedestrians have red, vehicles receive yellow for 1 second before returning to green.

The piezo uses slower pulses during idle and faster pulses during pedestrian crossing.

The assignment also requires non-blocking timing and interrupt-based button handling. See the sketch for the implementation.

### Uploading

1. Assemble the circuit using the report and task description.
2. Use a 220 Ω series resistor for each LED and a 10 kΩ pull-down resistor for the button.
3. Open `trafikklys.ino` in Arduino IDE.
4. If prompted, allow Arduino IDE to place it in a folder named `trafikklys`.
5. Select **Arduino Uno** and the appropriate serial port.
6. Compile and upload.
7. Test the idle state, request acknowledgement and complete crossing sequence.

Disconnect power before changing the wiring.

**Important:** The 9 Ω resistor used in the Python exercise is not the LED resistor value for the Arduino circuit.

## Circuit-Design Files

[Draft1.asc](./Draft1.asc) and [Draft2.asc](./Draft2.asc) are LTspice schematic files. Open them in LTspice to inspect their circuit designs.

Refer to the report for the documented circuit diagrams and component values.

## Related Documentation

- [Assignment overview](../README.md)
- [Original task description](../taskdescription.pdf)
- [My report](../oblig4_fridatbe.pdf)
- [LaTeX report source](../oblig4_fridatbe.tex)
- [Supporting media](../media/)
