# IR Sensor Calibration

Calibration helps each sensor distinguish the line from the background reliably. Different surfaces reflect infrared light differently, and readings can also change with mounting height, ambient light, and the threshold set by the sensor's potentiometer. Two sensors of the same type may not switch at exactly the same point.

> Do not assume black = 0 and white = 1. Measure the actual behaviour of the supplied sensor.

## Calibration procedure

1. Connect **one** IR sensor correctly.
2. Confirm its VCC, GND, and OUT wiring against the module labels.
3. Open Thonny and connect to the Pico.
4. Run the [single-sensor reading test](../electronics/README.md#reading-one-digital-sensor).
5. Hold the sensor at approximately its intended mounting height and keep that height consistent.
6. Place the sensor over the background surface.
7. Record the digital output shown in the Thonny Shell.
8. Place the sensor over the line.
9. Record the digital output again.
10. If the values do not switch reliably, make a small adjustment to the sensitivity potentiometer.
11. Repeat the background and line tests until the output switches reliably between the two surfaces.
12. Repeat the complete procedure for the second sensor; do not assume its best potentiometer position is identical.
13. Test both sensors under lighting similar to the event conditions.

Make small potentiometer adjustments and retest both surfaces after every change. Also check that the mounting is stable: changing the height or angle after calibration can change the result.

Calibration establishes what each sensor reports. It does not decide how the motors should respond; that remains part of the Makeathon challenge.

Related documentation: [IR sensor electronics](../electronics/README.md#ir-infrared-sensor-modules) · [sensor wiring](../wiring/pico_to_ir_sensors.md) · [digital inputs](../concepts/digital_inputs.md) · [troubleshooting](../troubleshooting/README.md)
