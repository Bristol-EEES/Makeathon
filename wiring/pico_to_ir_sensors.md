# Wiring the Pico to the IR Sensors

> Exact sensor model, pinout, supply requirements, and GPIO assignments are to be confirmed.

The [labelled IR sensor reference diagram](../electronics/README.md#ir-infrared-sensor-modules) shows the common `VCC`, `GND`, and `OUT` labels and the module's main parts. Confirm that the supplied sensor has the same pin order before connecting it.

Each sensor normally needs three functional connections: power (`VCC`), ground (`GND`), and an output signal. Do not rely on the physical order of pins; read the labels on the confirmed module.

| IR sensor pin | Connects to | Purpose |
|---|---|---|
| VCC | Appropriate confirmed power rail | Powers the sensor module |
| GND | Pico/system GND | Provides the common reference and return path |
| OUT | `Pico GPIO <TBD>` | Carries the digital sensor signal |

Both modules use the same three pin functions, but their `OUT` signals need separate Pico inputs:

| Device | Signal | Pico connection |
|---|---|---|
| Left IR sensor | OUT | `Pico GPIO <TBD>` |
| Right IR sensor | OUT | `Pico GPIO <TBD>` |

The Pico reads each output as a digital HIGH or LOW. Before connection, confirm that the sensor's output voltage cannot exceed the Pico GPIO's 3.3 V-safe range. A module powered at a higher voltage is not automatically safe for a Pico input.

Connect grounds before relying on a signal: without a common ground, the Pico and sensor may interpret voltages differently. With motor power off, test one sensor independently, observe how its output changes over light and dark surfaces, and then repeat for the other sensor. This also reveals whether HIGH means light or dark for the actual module.

VCC is a power input and OUT is a signal output; do not swap them. Verify the sensor's pin order and power requirements before switching on.

Next: [calibrate the IR sensors](../guides/ir_sensor_calibration.md) · [digital inputs](../concepts/digital_inputs.md) · [full-system wiring](full_system_wiring.md) · [pre-power check](../guides/pre_power_check.md) · [electronics guide](../electronics/README.md)
