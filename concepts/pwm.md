# PWM

**Pulse-width modulation (PWM)** switches a digital output on and off repeatedly. The percentage of each cycle spent on is the **duty cycle**.

```text
0%:   ____________________  always off
50%:  ‾‾__‾‾__‾‾__‾‾__‾‾  half of each cycle on
100%: ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾  always on
```

When PWM controls a motor driver, the rapid pulses change the average energy delivered to the motor. A larger duty cycle usually makes an unloaded motor turn faster, but load, battery condition, friction, and the motor driver also affect speed.

**Frequency** is the number of PWM cycles per second. It must be fast enough for useful control and suitable for the hardware, but there is no single correct value for every motor and driver.

See the [L298N electronics section](../electronics/README.md#l298n-motor-controller) and [Pico to L298N wiring](../wiring/pico_to_l298n.md).
