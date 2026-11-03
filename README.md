# Arduino Mechatronics Control System

Arduino, electronics and control-system coursework for **IN1080: Mechatronics** at the **University of Oslo**.

This repository collects Assignments **2–6**, including source code, reports and supporting experiment documentation. Topics include LED analysis, traffic-light control, servo operation, I²C communication, software-generated PWM and PID motor control.

**Author:** Frida Berge (`fridatbe`)

## Assignments

| Assignment | Contents | Folder |
| --- | --- | --- |
| 2 | Assignment 2 coursework and documentation | [oblig2](./oblig2/) |
| 3 | Assignment 3 coursework and documentation | [oblig3](./oblig3/) |
| 4 | LED current calculations, circuit-design files and an Arduino traffic-light controller | [oblig4](./oblig4/) |
| 5 | Light-controlled servo and I²C communication between three Arduino boards | [oblig5](./oblig5/) |
| 6 | DC-motor control with software PWM and a homemade servo with PID position control | [oblig6](./oblig6/) |

See each assignment folder for its task description, implementation and report.

## Repository Structure

```text
arduino-mechatronics-control-system/
├── README.md
├── oblig2/
├── oblig3/
├── oblig4/
│   ├── code/
│   ├── media/
│   └── reports and task description
├── oblig5/
│   ├── code/
│   ├── media/
│   └── reports and task description
└── oblig6/
    ├── code/
    ├── media/
    └── reports and task description
```

The tree above is an overview rather than a complete file listing.

## Assignment Highlights

### Assignment 4 — LED Analysis and Traffic Lights

The code includes:

- Python calculations for Tasks 1 and 5 of the LED exercise.
- LTspice circuit-design files.
- An Arduino sketch for a pedestrian-crossing traffic light.

The traffic-light task combines vehicle and pedestrian LEDs, a request button, an acknowledgement LED and a piezo sounder.

**Documentation:** [Assignment overview](./oblig4/README.md) · [Code](./oblig4/code/README.md)

### Assignment 5 — Servo Control and I²C

**Task 1:** Use a phototransistor to measure light intensity and a servo to indicate the reading.

**Task 2:** Connect three Arduino boards over I²C. One controller receives mouse-click input from Processing and forwards it alternately to two receiving boards, which toggle their built-in LEDs.

Supporting media include the servo setup photo, demonstration video, I²C setup photo and communication capture.

Task 2 was completed with two other students. See the report and source-code comments for collaborator details.

**Documentation:** [Assignment overview](./oblig5/README.md) · [Code](./oblig5/code/README.md) · [Media](./oblig5/media/README.md)

### Assignment 6 — PWM and PID Motor Control

**Task 1:** Control a DC motor through an L293D driver using non-blocking software PWM. A potentiometer adjusts the duty cycle, and Analog Discovery 2 is used to inspect the output signals.

**Task 2:** Build a servo using a DC motor and mechanically coupled feedback potentiometer. A second potentiometer provides the target position, and a PID controller regulates the motor.

Supporting media document the motor circuit, measurement setup, PWM waveform and homemade servo assembly.

**Documentation:** [Assignment overview](./oblig6/README.md) · [Code](./oblig6/code/README.md) · [Media](./oblig6/media/README.md)

## Software and Tools

Tools used across the assignments include:

| Tool | Purpose |
| --- | --- |
| Arduino IDE | Compile and upload Arduino sketches |
| Python 3 | Numerical calculations and plotting |
| NumPy and Matplotlib | Python analysis and visualization |
| LTspice | Inspect circuit schematics |
| Processing | Mouse-click input and the course-provided PID tuning interface |
| ControlP5 | GUI library for the Processing PID interface |
| WaveForms | Oscilloscope measurements and I²C protocol analysis |
| LaTeX | Report preparation |

Requirements vary by assignment. Consult the relevant code README before running an experiment.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/fridaberge/arduino-mechatronics-control-system.git
cd arduino-mechatronics-control-system
```

### 2. Choose an Assignment

Open its folder and read the task description, report and available README files.

### 3. Run the Relevant Code

#### Arduino

1. Assemble the circuit according to the assignment documentation.
2. Check the sketch's pin assignments against the wiring.
3. Open the `.ino` file in Arduino IDE.
4. Select the board and serial port.
5. Compile and upload.

Open each program as a separate sketch. If Arduino IDE asks to move a sketch into a folder with the same name, allow it.

#### Python

For the Assignment 4 scripts:

```bash
python -m pip install numpy matplotlib
cd oblig4/code
python oblig4_1.py
python oblig4_5.py
```

#### Processing and Measurement Tools

Some experiments depend on course-provided Processing programs or external measurement equipment. These resources may not be included in this repository.

See the assignment documentation for setup instructions.

## Reports and Media

Reports describe the experiments, calculations and results. LaTeX files provide the report source where included.

The `media/` folders contain supporting photos, screenshots and videos. GitHub may offer video files for download rather than play them directly in a README.

## Hardware Safety

- Disconnect power before changing wiring.
- Check supply voltages, component polarity and pin assignments.
- Use suitable current-limiting resistors for LEDs.
- Do not drive a DC motor directly from an Arduino I/O pin.
- Use a common ground where required by the circuit.
- Avoid driving mechanically coupled potentiometers beyond their travel limits.
- Preserve safety functions in course-provided motor-control templates.
- Follow the course's laboratory safety procedures.

## Attribution and Collaboration

Assignment instructions, reference diagrams and starter code were provided by **IN1080: Mechatronics**.

Task 2 of Assignment 5 was completed collaboratively. Participant details belong in the corresponding report and code comments.

This repository documents coursework. If you are taking the same course, follow its academic-integrity rules and complete your own submission.
```
