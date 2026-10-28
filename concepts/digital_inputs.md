# Digital Inputs

A digital input reduces a voltage to one of two logical states: **HIGH** or **LOW**. The Pico can read the digital output of an IR sensor module and use that state in a decision.

Many sensor modules create their digital output by comparing a measured reflection level with a **threshold**. One side of the threshold becomes HIGH and the other becomes LOW. Determine the mapping during calibration because HIGH may represent either the line or the background.

Real electrical signals are not perfectly clean. A reading near the threshold may switch back and forth because of noise, vibration, changing height, ambient light, or an uneven surface. Useful responses include improving wiring and mounting, adjusting the sensor threshold, or requiring a reading to remain stable briefly. This last idea is similar to **debouncing** a switch.

Do not hide a consistently poor signal with software; first check the hardware and calibrate on the course surface. See [IR sensors](../electronics/README.md#ir-infrared-sensor-modules) and [sensor wiring](../wiring/pico_to_ir_sensors.md).
