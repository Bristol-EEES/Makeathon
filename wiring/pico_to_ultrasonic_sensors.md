# Wiring the Pico to the Ultrasonic Sensors

The supplied diagram identifies an HC-SR04-style module with four pins: VCC, Trig, Echo, and GND. Confirm that both supplied boards match the diagram before connecting them.

> Exact Pico GPIO assignments and the final ultrasonic-sensor power and Echo level-conditioning circuit are to be confirmed.

## Pin-purpose table

| Sensor pin | Connects to | Purpose |
|---|---|---|
| VCC | Confirmed sensor power rail | Powers the ultrasonic module |
| Trig | `Pico GPIO <TBD>` | Receives a short output pulse from the Pico to begin a measurement |
| Echo | Approved level conditioning, then `Pico GPIO <TBD>` | Sends a timed input pulse back to the Pico |
| GND | Pico/system GND | Provides the common electrical reference and return path |

Each of the two sensors normally needs its own Trig GPIO and Echo GPIO:

| Device | Signal | Pico connection |
|---|---|---|
| Left ultrasonic sensor | Trig | `Pico GPIO <TBD>` |
| Left ultrasonic sensor | Echo | Approved level conditioning → `Pico GPIO <TBD>` |
| Right ultrasonic sensor | Trig | `Pico GPIO <TBD>` |
| Right ultrasonic sensor | Echo | Approved level conditioning → `Pico GPIO <TBD>` |

## Echo voltage warning

Standard HC-SR04 modules are commonly powered from 5 V and can produce a 5 V HIGH signal on Echo. Raspberry Pi Pico GPIO uses 3.3 V logic and is not intended to receive 5 V.

> Do not connect Echo directly to a Pico GPIO until the supplied module's output voltage and the approved level-conditioning circuit have been confirmed.

The final wiring may use an appropriate voltage divider or logic-level shifter. Do not invent resistor values or bypass that protection. Trig is a low-current control signal, not a power connection.

## Safe first test

1. Disconnect motor and battery power.
2. Confirm the sensor pin order from its labels.
3. Confirm the approved VCC supply and Echo level conditioning.
4. Connect the common ground.
5. Connect one sensor's Trig and conditioned Echo signals to the assigned Pico GPIO pins.
6. Test that sensor by itself before adding the second.
7. When testing both sensors, trigger them separately to reduce ultrasonic crosstalk.

See the [ultrasonic electronics and code example](../electronics/README.md#ultrasonic-distance-sensors), [distance-measurement concept](../concepts/ultrasonic_distance.md), [full-system wiring](full_system_wiring.md), and [pre-power check](../guides/pre_power_check.md).
