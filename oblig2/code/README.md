# Code — Assignment 2

Python scripts and Arduino sketches used for the voltage-divider assignment in **IN1080: Mechatronics**.

## Contents

| File type | Purpose |
| --- | --- |
| `.py` | Calculations and plots for the resistor and voltage-divider tasks |
| `.ino` | Arduino analog-input readings and serial output for the practical experiments |

The original submission naming requirements are listed in [taskdescription.md](../taskdescription.md).

## Python Scripts

The Python tasks investigate:

- Current through a 100 Ω resistor as a function of applied voltage.
- Voltage-divider output as a function of the lower resistance.

### Dependencies

```bash
python -m pip install numpy matplotlib
```

### Running

From this folder, run the relevant script:

```bash
python <filename>.py
```

Replace `<filename>` with the script’s actual name.

The code reproduced in the report saves plots as `opg1.png` and `opg2.png`. Unless the output path has been changed, these files are written to the current working directory—not automatically to `../media/`.

## Arduino Sketches

The Arduino experiments read the divider output through **A0** and send the readings to the computer through the serial connection.

### Running

1. Build the circuit described in the relevant task.
2. Open the `.ino` file in Arduino IDE.
3. Select the board and serial port.
4. Compile and upload the sketch.
5. Open Serial Monitor or Serial Plotter.
6. Use the baud rate specified by `Serial.begin()` in the sketch.

Arduino IDE expects a sketch folder to have the same name as its main `.ino` file. If prompted, allow the IDE to create or move the sketch into the matching folder.

### Reading the Output

`analogRead()` returns a raw ADC reading, not a voltage directly. Its range and voltage interpretation depend on the board’s ADC resolution and reference voltage.

Task 5 requires five readings per second. Check the implementation’s delay and execution time when comparing it with that requirement.

## Related Documentation

- [Assignment overview](../README.md)
- [Task description](../taskdescription.md)
- [My answers and reflections](../oblig2_fridatbe.pdf)
- [Supporting media](../media/)

## Attribution

These files contain my code submitted for the assignment. The tasks and circuit requirements were provided by the course.
