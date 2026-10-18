# Full-System Wiring

This page gives a high-level map of the robot. It intentionally uses symbolic labels until the final hardware and pin assignment are confirmed.

> Exact GPIO assignments, sensor pinout and voltage, L298N module configuration, motor specifications, and battery chemistry are to be confirmed.

> The final standalone power connection for the Raspberry Pi Pico is still to be confirmed. Follow the final Makeathon wiring diagram once published.

## Connection table

| From | To | Function |
|---|---|---|
| Left IR sensor output | `Pico GPIO <TBD>` | Left digital sensor input |
| Right IR sensor output | `Pico GPIO <TBD>` | Right digital sensor input |
| Sensor VCC pins | Confirmed safe sensor supply | Sensor power |
| Sensor GND pins | System/Pico GND | Common reference |
| `Pico GPIO <TBD>` × 4 | L298N IN1, IN2, IN3, IN4 | Direction control |
| `Pico PWM GPIO <TBD>` | L298N ENA, if PWM is used | Motor A speed/enable |
| `Pico PWM GPIO <TBD>` | L298N ENB, if PWM is used | Motor B speed/enable |
| Pico GND | L298N/system GND | Common control reference |
| Battery positive | Confirmed L298N motor-supply positive | Motor power |
| Battery negative | L298N motor-supply ground | Motor power return |
| L298N Motor A outputs | One DC motor | Motor A drive |
| L298N Motor B outputs | Other DC motor | Motor B drive |

Do not infer a power connection from this table where the final design is still marked TBD.

## System diagram

```text
                         signal wires
 [Left IR sensor]  ----------------------\
   VCC: confirmed supply                  \
   GND: system ground                      > [Pico] -- IN1..IN4 / ENA..ENB --> [L298N]
 [Right IR sensor] -----------------------/      |                                |  |
   VCC: confirmed supply                         +---------- common GND ----------+  |
   GND: system ground                                                                 |
                                                                 [Motor A] <----------+
 [Battery +] -------- motor-supply positive --------------------> [L298N]
 [Battery -] -------- motor-supply ground ----------------------> [L298N] ---> [Motor B]
```

Motor current must travel through the battery–motor-driver–motor path, never through Pico GPIO.

## Final Event Wiring Diagram

> A final labelled wiring diagram will be added once the GPIO assignments, sensor electrical requirements, L298N jumper configuration, battery chemistry, and Pico power arrangement have been confirmed.

The conceptual diagram above remains useful for understanding signal and power paths, but it is not a substitute for the final event wiring diagram.

## Before Powering On

- [ ] Battery polarity matches the confirmed motor-supply terminals.
- [ ] No bare wires or connected breadboard rows create a short.
- [ ] Motor current is not routed through the Pico or its GPIO pins.
- [ ] Both motors connect only to L298N motor outputs.
- [ ] Pico, L298N, and sensors share ground where the design requires it.
- [ ] Sensor supply and output voltages are safe for Pico GPIO.
- [ ] Every TBD has been replaced by a confirmed event wiring assignment.
- [ ] L298N jumpers and power terminals match the supplied module's instructions.
- [ ] Loose wires are secured, and wheels can spin safely during the first test.
- [ ] Power is off while making the final inspection.

Detailed pages: [Pico to sensors](pico_to_ir_sensors.md) · [Pico to L298N](pico_to_l298n.md) · [motors to L298N](motors_to_l298n.md) · [battery pack](battery_pack.md) · [pre-power check](../guides/pre_power_check.md) · [electronics guide](../electronics/README.md)
