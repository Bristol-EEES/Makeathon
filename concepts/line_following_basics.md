# Line-Following Basics

A line-following robot uses sensors to estimate the position of a line and adjusts its motors to stay near it. With two sensors, one is normally placed to the left and one to the right of the intended path.

The controller runs a **feedback loop**:

```text
Read sensors
Determine where the line is
Choose a correction
Adjust motors
Repeat
```

If the sensor pattern suggests the robot has moved to one side, it can make a left or right correction by changing the relative wheel speeds. The exact meaning of each pattern depends on sensor placement, whether the course uses a dark-on-light or light-on-dark line, and the tested HIGH/LOW sense. You must determine these rather than assume them.

A proportional idea makes a larger correction when the estimated error is larger, but two digital sensors provide only a small number of states. They cannot measure the line position continuously and may not distinguish every situation, such as losing the line versus encountering some junctions.

Calibration is essential. Set and test sensor height, spacing, alignment, and thresholds on the real surface under representative lighting. Test sensing and motor direction separately before combining them.

This page deliberately describes the method without supplying a finished implementation. See [digital inputs](digital_inputs.md), [motor direction](motor_direction.md), and the [IR sensor overview](../electronics/README.md#ir-infrared-sensor-modules).
