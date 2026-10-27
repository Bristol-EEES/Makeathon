# Wiring the Battery Pack

The four-AA battery holder provides the robot's nominal 6 V source.

| Battery connection | Destination |
|---|---|
| Positive (`+`) | L298N motor-supply positive terminal |
| Negative (`-`) | L298N GND/common GND |

The L298N `5V` terminal supplies Pico `VSYS` and both HC-SR04 VCC pins. Do not connect the nominal 6 V battery output directly to Pico `VSYS` or `3V3(OUT)`.

Battery negative, L298N GND, Pico GND, both IR sensor grounds, and both ultrasonic sensor grounds form the common GND rail. Remove batteries and disconnect USB before changing wiring.

## Safety

- Verify polarity from the holder markings rather than wire colour alone.
- Never allow the positive and negative leads to touch.
- Do not route motor power through Pico GPIO or breadboard signal rows.
- Check for stray strands and exposed conductors.
- Stop immediately if a wire, battery, or module becomes unexpectedly hot.

See [full-system wiring](full_system_wiring.md), the [electronics guide](../electronics/README.md), and the [pre-power check](../guides/pre_power_check.md).
