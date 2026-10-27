# Wiring the Pico to the HC-SR04 Sensors

Two standard HC-SR04-style sensors are powered from the 5 V rail. Pico GPIO uses 3.3 V logic, so each sensor requires its own Trig GPIO, Echo GPIO, and Echo voltage divider.

| HC-SR04 pin | Connection | Notes |
|---|---|---|
| VCC | Confirmed 5 V rail | Sensor power, not a GPIO signal |
| GND | Common GND | Shared Pico/sensor voltage reference |
| TRIG | Pico GPIO | Direct 3.3 V output from the Pico; no divider required |
| ECHO | Divider, then Pico GPIO | Never connect raw 5 V Echo directly to the Pico |

### Ultrasonic sensor 1

| Function | Pico GPIO | Physical pin |
|---|---:|---:|
| TRIG | GP10 | 14 |
| ECHO after divider | GP11 | 15 |

### Ultrasonic sensor 2

| Function | Pico GPIO | Physical pin |
|---|---:|---:|
| TRIG | GP12 | 16 |
| ECHO after divider | GP13 | 17 |

VCC is the 5 V power connection. TRIG is an **input to the HC-SR04**, driven directly by the Pico: GP10 or GP12 sends a 3.3 V HIGH, which is commonly sufficient for a standard HC-SR04. ECHO is an **output from the HC-SR04**. Because the sensor is powered from 5 V, ECHO may rise to approximately 5 V and must never connect directly to Pico GPIO.

> A component may be powered from 5 V while still communicating safely with a 3.3 V microcontroller, provided signal voltages are compatible.

## Echo voltage dividers

> **DIAGRAM PLACEHOLDER — HC-SR04 Echo Voltage Divider**
>
> Show HC-SR04 ECHO passing through a 1 kΩ / 2 kΩ divider before reaching the Pico GPIO input.

For **each** sensor:

1. Connect a 1 kΩ resistor from HC-SR04 ECHO to a Pico-input node.
2. Connect a 2 kΩ resistor from that node to common GND.
3. Connect sensor #1's node to GP11 or sensor #2's node to GP13.

The standard divider equation is `Vout = Vin × R2 / (R1 + R2)`. Here, `Vin ≈ 5 V`, `R1 = 1 kΩ`, and `R2 = 2 kΩ`, so `Vout ≈ 5 × 2 / (1 + 2) ≈ 3.33 V`. This makes the Echo signal appropriate for the Pico's 3.3 V GPIO domain.

Use two 1 kΩ and two 2 kΩ resistors in total. Do not share one divider between two Echo outputs. These resistors reduce the Echo **signal**; no divider belongs on VCC, and a divider must not power the Pico.

## Supply voltage and logic voltage

| Type | Example | Meaning |
|---|---|---|
| Supply voltage | 5 V rail to HC-SR04 VCC | Powers the sensor |
| Logic input | Pico 3.3 V GPIO to TRIG | Pico sends a command to the sensor |
| Logic output | HC-SR04 ECHO through divider to Pico GPIO | Sensor returns a Pico-safe pulse |

Powering the Pico through 5 V on `VSYS` does not make its GPIO 5 V tolerant. GPIO remains in the 3.3 V logic domain.

## Safe testing procedure

1. Remove battery and USB power before wiring.
2. Check the VCC, Trig, Echo, and GND labels on both modules.
3. Build and inspect both dividers.
4. Confirm all grounds connect to common GND.
5. Test HC-SR04 #1 on GP10/GP11 facing a large solid object.
6. Test HC-SR04 #2 on GP12/GP13 separately.
7. Trigger the sensors one at a time to reduce ultrasonic interference.

See the [isolated code examples](../electronics/README.md#ultrasonic-distance-sensors), [distance concept](../concepts/ultrasonic_distance.md), [full-system wiring](full_system_wiring.md), and [troubleshooting](../troubleshooting/README.md).
