# PWM

**Pulse-width modulation (PWM)** switches a digital output on and off repeatedly. The percentage of each cycle spent on is the **duty cycle**.

```text
0%:   ____________________  always off
50%:  ‾‾__‾‾__‾‾__‾‾__‾‾  half of each cycle on
100%: ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾  always on
```

When PWM controls a motor driver, the rapid pulses change the average energy delivered to the motor. The duty cycle is the **PWM command** requested by the Pico; it is not a direct measurement of physical motor speed. A 50% PWM command does not mean that the wheel turns at exactly 50% of its maximum speed.

Actual motor speed depends on the motor, battery voltage, L298N voltage drop, mechanical load, friction, wheel contact, and startup or stall behaviour. A motor also usually needs more torque and current to start than it needs to continue turning. At a low duty cycle it may hum or twitch without starting, even though the same duty cycle can keep it moving once it is already rotating.

During isolated testing, begin by checking that the motor can start at a high duty cycle, then reduce the command gradually to find a reliable running range. Do not assume one universal minimum value for every motor or robot.

A program can sometimes apply a short, higher startup command before reducing to a lower running command. This **startup kick** is only a concept: its level and duration must be tested for the supplied motors, and it does not determine how sensor readings should control the robot.

**Frequency** is the number of PWM cycles per second. It must be fast enough for useful control and suitable for the hardware, but there is no single correct value for every motor and driver.

See the [L298N electronics section](../electronics/README.md#l298n-motor-controller) and [Pico to L298N wiring](../wiring/pico_to_l298n.md).
