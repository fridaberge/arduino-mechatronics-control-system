# Code — Assignment 5

Arduino sketches for **IN1080: Mechatronics**, Assignment 5: light-controlled servo operation and I²C communication.

## Files

| File | Purpose |
| --- | --- |
| [oblig5_1_fridatbe.ino](./oblig5_1_fridatbe.ino) | Task 1: Light-controlled servo |
| [oblig5_2_fridatbe.ino](./oblig5_2_fridatbe.ino) | Additional Task 2 sketch; consult its contents for its role |
| [oblig5_i2cmaster_fridatbe.ino](./oblig5_i2cmaster_fridatbe.ino) | Task 2: I²C controller |
| [oblig5_i2cslave1_fridatbe.ino](./oblig5_i2cslave1_fridatbe.ino) | Task 2: First I²C receiver |
| [oblig5_i2cslave2_fridatbe.ino](./oblig5_i2cslave2_fridatbe.ino) | Task 2: Second I²C receiver |

## Task 1 — Light-Controlled Servo

**Sketch:** [oblig5_1_fridatbe.ino](./oblig5_1_fridatbe.ino)

The task uses a phototransistor reading to set a servo's angular position.

### Main Concepts

- Read the light sensor using `analogRead()`.
- Map readings from 0–1023 to an angle from 0–180 degrees.
- Control the servo using `Servo.h`.

### Running the Sketch

1. Assemble the servo and sensor circuit according to the task description.
2. Check the sketch for the sensor and servo pin assignments.
3. Open `oblig5_1_fridatbe.ino` in Arduino IDE.
4. Select **Arduino Uno** and the correct serial port.
5. Compile and upload.
6. Vary the light reaching the phototransistor and observe the servo.

See the [setup photo](../media/bilde_servo.jpg) and [demonstration video](../media/video_servo.mp4).

## Task 2 — I²C Communication

The task uses three Arduino boards:

- One controller receiving mouse-click input from Processing over serial.
- Two receivers, each toggling its built-in LED when addressed.

Communication uses the built-in `Wire.h` library.

### Controller

**Sketch:** [oblig5_i2cmaster_fridatbe.ino](./oblig5_i2cmaster_fridatbe.ino)

The controller's task is to forward successive mouse-click inputs alternately to the two receiver addresses.

### Receivers

**Sketches:**

- [oblig5_i2cslave1_fridatbe.ino](./oblig5_i2cslave1_fridatbe.ino)
- [oblig5_i2cslave2_fridatbe.ino](./oblig5_i2cslave2_fridatbe.ino)

Each receiver listens at its own I²C address and toggles its built-in LED when input is received. The assignment recommends `Wire.onReceive()` for handling incoming transmissions.

Check the sketches for the actual addresses and ensure they match the controller's destination addresses.

### Wiring

| Signal | Connection between boards |
| --- | --- |
| SDA | A4 to A4 |
| SCL | A5 to A5 |
| Ground | GND to GND |

Power each Arduino through its own USB cable.

### Running the Experiment

1. Upload the controller sketch to the controller board.
2. Upload the first receiver sketch to one receiving board.
3. Upload the second receiver sketch to the other receiving board.
4. Disconnect power while completing or changing the bus wiring.
5. Reconnect each board's USB power.
6. Run the Processing mouse-click program from Assignment 1.
7. Select the controller's serial port and match the baud rate used by its sketch.
8. Click repeatedly and observe the receiver LEDs.

If Arduino IDE prompts you to move a sketch into a matching folder, allow it. Each `.ino` sketch should be opened separately rather than combined into one sketch folder.

### Expected Behavior

| Click | Receiver 1 LED | Receiver 2 LED |
| --- | --- | --- |
| Initial state | Off | Off |
| 1 | On | Off |
| 2 | On | On |
| 3 | Off | On |
| 4 | Off | Off |

This table describes the assignment's expected sequence starting with both LEDs off.

### Inspecting the Bus

Use Analog Discovery 2 and the WaveForms Protocol Analyzer:

1. Connect SDA and SCL to two digital inputs.
2. Connect the instrument ground to the circuit ground.
3. Select the corresponding inputs in the I²C decoder.
4. Start receiving data and generate mouse clicks.
5. Inspect the decoded addresses and transmitted data.

The assignment notes that Processing may occasionally register two clicks instead of one. A bus capture can help identify duplicate transmissions.

See the [I²C capture](../media/screen.png).

## Collaboration

Task 2 was completed with two other students.

The Task 2 sketch comments should list all three usernames, as required by the assignment.

## Related Documentation

- [Assignment overview](../README.md)
- [Original task description](../taskdescription.pdf)
- [My report](../oblig5_fridatbe.pdf)
- [Media documentation](../media/README.md)
