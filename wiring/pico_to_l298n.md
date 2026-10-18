# Wiring the Pico to the L298N

> Exact Pico GPIO assignments and the supplied L298N module layout are to be confirmed.

Use the [labelled L298N reference diagram](../electronics/README.md#l298n-motor-controller) to identify the usual terminal names, but check them against the supplied board. The diagram is a reference pinout, not the final Makeathon wiring scheme.

The Pico sends low-current control signals to the motor driver. It does not send motor power through its GPIO pins.

| L298N pin | Pico connection | Purpose |
|---|---|---|
| IN1 | `Pico GPIO <TBD>` | Motor A direction control |
| IN2 | `Pico GPIO <TBD>` | Motor A direction control |
| ENA | `Pico PWM GPIO <TBD>` or confirmed jumper arrangement | Motor A speed/enable |
| IN3 | `Pico GPIO <TBD>` | Motor B direction control |
| IN4 | `Pico GPIO <TBD>` | Motor B direction control |
| ENB | `Pico PWM GPIO <TBD>` or confirmed jumper arrangement | Motor B speed/enable |
| GND | Pico GND | Common signal reference and return path |

Some L298N modules use removable jumpers on ENA and ENB. On a typical module, a fitted jumper holds its channel enabled continuously—equivalent to a 100% enable command—while removing it allows the EN pin to receive PWM from the Pico. This does not guarantee 100% physical motor speed.

Confirm the supplied board before removing a jumper or applying PWM. Never manually short ENA and ENB together or connect an enable pin to an unconfirmed power terminal. The module's motor supply, logic supply, regulator arrangement, and final jumper arrangement must all be confirmed from its labels and documentation.

## Safe connection order

1. Switch off and disconnect motor and USB power.
2. Confirm the module terminal labels and jumper arrangement.
3. Connect the common ground.
4. Connect the direction and, if used, enable/PWM signals.
5. Connect motors and motor power using their separate paths.
6. Complete the pre-power inspection before applying power.

Never connect a motor to Pico GPIO or route motor current through the Pico. See [GPIO limits](../concepts/gpio.md), [PWM](../concepts/pwm.md), [full-system wiring](full_system_wiring.md), and the [pre-power check](../guides/pre_power_check.md).
