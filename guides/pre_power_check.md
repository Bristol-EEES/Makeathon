# Pre-Power Check

Complete every check before inserting batteries or applying USB power. Remove all power before correcting a failed check.

If any power pin, voltage, common-ground connection, motor-driver control, or Echo divider is unfamiliar, review the [Electronics Guide](../electronics/README.md) before completing this checklist.

## Power

- [ ] Battery positive connects to the L298N motor-supply positive terminal.
- [ ] Battery negative connects to L298N GND/common GND.
- [ ] L298N `5V` connects to Pico `VSYS`.
- [ ] L298N `5V` connects to both HC-SR04 VCC pins.
- [ ] Pico `3V3(OUT)` connects to both IR sensor VCC pins.
- [ ] The nominal 6 V battery output does not connect directly to Pico `VSYS`, `3V3(OUT)`, or GPIO.
- [ ] `VBUS` is not being used as the untethered robot supply.
- [ ] Pico GND, L298N GND, battery negative, both IR grounds, and both ultrasonic grounds share common GND.

## Signals

- [ ] GP2 and GP3 connect to L298N IN1 and IN2.
- [ ] GP4 connects to L298N ENA.
- [ ] GP6 and GP7 connect to L298N IN3 and IN4.
- [ ] GP8 connects to L298N ENB.
- [ ] GP10 and GP12 connect to HC-SR04 #1 and #2 TRIG respectively.
- [ ] Each HC-SR04 GND connects to common GND.
- [ ] TRIG connects directly from GP10/GP12 to the corresponding sensor input without an Echo divider.
- [ ] HC-SR04 #1 ECHO reaches GP11 only through its own 1 kΩ/2 kΩ divider.
- [ ] HC-SR04 #2 ECHO reaches GP13 only through its own 1 kΩ/2 kΩ divider.
- [ ] Each 1 kΩ resistor runs from ECHO to its divider midpoint.
- [ ] Each divider midpoint connects to the correct Pico Echo input: GP11 or GP13.
- [ ] Each lower 2 kΩ resistor runs from its divider midpoint to common GND.
- [ ] No raw 5 V Echo signal connects to Pico GPIO.
- [ ] Left IR OUT connects to GP14 and right IR OUT connects to GP15.

## Motors and physical inspection

- [ ] Left motor connects only to L298N OUT1/OUT2.
- [ ] Right motor connects only to L298N OUT3/OUT4.
- [ ] No motor connects to Pico GPIO.
- [ ] ENA and ENB jumpers are removed if they permanently hold the inputs HIGH, allowing GP4 and GP8 PWM control.
- [ ] The separate 5V-EN/regulator jumper is configured for the documented 5 V rail and has not been confused with ENA/ENB.
- [ ] No breadboard row or bare wire creates a short.
- [ ] No loose wire can touch another terminal or a wheel.
- [ ] Batteries follow the holder's marked orientation.
- [ ] The robot is raised or restrained for its first motor test.

Use the authoritative [full-system wiring table](../wiring/full_system_wiring.md) during inspection.
