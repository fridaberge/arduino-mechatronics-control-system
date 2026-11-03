# Code — Assignment 6

Arduino sketches for **IN1080: Mechatronics**, Assignment 6.

## Files

| File | Task |
| --- | --- |
| [fridatbe_oblig6_opg1.ino](./fridatbe_oblig6_opg1.ino) | Task 1: Software PWM for DC-motor control |
| [fridatbe_oblig6_opg2.ino](./fridatbe_oblig6_opg2.ino) | Task 2: Homemade servo with PID position control |

## Task 1 — Software PWM

**Sketch:** [fridatbe_oblig6_opg1.ino](./fridatbe_oblig6_opg1.ino)

### Purpose

Control a DC motor through an L293D driver, using potentiometer input to adjust the PWM duty cycle.

### Assignment Requirements

- Generate PWM on Arduino pin 10 using `digitalWrite()`.
- Do not use `analogWrite()`.
- Do not use blocking code.
- Adjust the duty cycle from a potentiometer reading.
- Use a suitable PWM frequency: approximately 100 Hz is recommended, with a stated upper limit of 5 kHz for the exercise.

Consult the sketch for its timing implementation and remaining pin assignments.

### Running the Sketch

1. Assemble the Task 1 circuit according to the assignment diagram.
2. Check the wiring, battery polarity and common ground.
3. Open `fridatbe_oblig6_opg1.ino` in Arduino IDE.
4. Select **Arduino Uno** and the correct serial port.
5. Compile and upload.
6. Turn the potentiometer and observe the motor's response.

### Measuring the PWM Signal

Use Analog Discovery 2 and WaveForms:

1. With power disconnected, connect each motor-driver output to the positive input of an oscilloscope channel.
2. Connect both negative channel inputs to circuit ground.
3. Restore power and open **Scope** in WaveForms.
4. Adjust the potentiometer to approximately 50% duty cycle.
5. Capture the signals and inspect the waveform.

See the [measurement setup](../media/bilde_oppsett.jpg) and [waveform capture](../media/screen.png).

## Task 2 — PID Position Control

**Sketch:** [fridatbe_oblig6_opg2.ino](./fridatbe_oblig6_opg2.ino)

### Purpose

Use a DC motor and a mechanically coupled potentiometer to build a position-controlled servo.

A second potentiometer supplies the desired position. The PID controller uses the difference between the target and measured positions to determine the motor-control output.

### Assignment Requirements

- Implement PID position control.
- Reuse the software-generated PWM approach from Task 1.
- Complete the missing sections of the supplied template.
- Preserve the template's existing functions and safety features.
- Test with the default PID values before tuning.
- Document the chosen PID parameters in the report.

Although parts of the assignment text refer to PWM from “Task 2,” the PWM implementation is introduced in Task 1.

### Running the Sketch

1. Assemble the motor, bracket, coupler and feedback potentiometer.
2. Connect the circuit according to the Task 2 diagram.
3. Confirm that both potentiometers are wired in the same orientation.
4. Check the sketch's pin assignments against the wiring.
5. Open `fridatbe_oblig6_opg2.ino` in Arduino IDE.
6. Select **Arduino Uno** and the correct serial port.
7. Compile and upload.
8. Test cautiously with the default PID parameters.
9. Change the target position and observe whether the motor moves toward it and settles.

Disconnect power immediately if the motor drives toward a mechanical stop or the feedback direction is incorrect.

### Optional PID Tuning Interface

The course provides a Processing program for adjusting PID parameters.

To use it:

1. Install Processing.
2. Install **ControlP5** through:
   **Sketch → Import Library → Manage Libraries**.
3. Confirm that the Arduino sketch works with the default PID values.
4. Run the course-provided interface and configure the serial connection as required by that program.
5. Adjust the parameters and record the selected values in the report.

The Processing program is not included in the file listing for this folder.

## Opening the Sketches

Open each `.ino` file as a separate sketch. If Arduino IDE asks to move a file into a folder with the same name, allow it.

Do not place both files into one Arduino sketch folder, since they are separate programs.

## Safety

- Disconnect power before rewiring.
- Check motor-driver supply connections and battery polarity.
- Keep the motor and control circuits referenced to a common ground.
- Do not exceed the potentiometer's mechanical travel.
- Preserve the supplied template's safety logic.

## Related Documentation

- [Assignment overview](../README.md)
- [Task description](../Taskdescription.pdf)
- [Written report](../fridatbe_oblig6.pdf)
- [Media documentation](../media/README.md)
