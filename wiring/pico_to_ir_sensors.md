# Wiring the Pico to the IR Sensors

Each IR line sensor has VCC, GND, and OUT. Check the printed labels because physical pin order can vary.

| Sensor | VCC | GND | OUT |
|---|---|---|---|
| Left IR sensor | Pico `3V3(OUT)` | Common GND | Pico GP14, physical pin 19 |
| Right IR sensor | Pico `3V3(OUT)` | Common GND | Pico GP15, physical pin 20 |

Powering these sensors from the Pico's regulated 3.3 V output keeps their digital outputs in the Pico's 3.3 V logic domain. `3V3(OUT)` is a power output; OUT is the sensor's signal. Do not swap them.

The Pico reads GP14 and GP15 as digital HIGH or LOW. The electrical connections are final, but teams must still calibrate both modules over the actual light background and dark line to discover their HIGH/LOW sense and suitable threshold. A dark line normally reflects less infrared light than the lighter background.

Remove power before changing connections. All grounds must join the common GND rail.

Next: [calibrate the IR sensors](../guides/ir_sensor_calibration.md) · [digital inputs](../concepts/digital_inputs.md) · [full-system wiring](full_system_wiring.md) · [pre-power check](../guides/pre_power_check.md)
