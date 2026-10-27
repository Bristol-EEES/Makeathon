# Ultrasonic Distance Measurement

An ultrasonic distance sensor estimates how far away an object is by measuring the travel time of a sound pulse. **Ultrasonic** means that the sound frequency is above the normal range of human hearing.

## Time of flight

The measurement follows four steps:

1. The Pico sends a short trigger pulse to the sensor.
2. The sensor transmits a burst of ultrasonic sound.
3. The sound reflects from an object and returns to the receiver.
4. The sensor produces an Echo pulse whose duration represents the sound's round-trip travel time.

The distance calculation is:

```text
distance = (echo time × speed of sound) ÷ 2
```

Division by two is essential because the measured time includes the outward journey to the object and the return journey to the sensor.

At approximately room temperature, sound travels through air at about 343 metres per second, or 0.0343 centimetres per microsecond. Temperature and air conditions change this value slightly, so the result is an estimate rather than a perfect measurement.

## Why readings vary

Ultrasonic measurements work best when a reasonably large, solid surface faces the sensor. Readings can be poor or absent when:

- the object is too close or too far away for the module;
- the surface is angled and reflects sound away from the receiver;
- the object is small, soft, or sound-absorbing;
- the sensor or object moves during a reading;
- nearby ultrasonic sensors interfere with one another; or
- no echo returns before the software timeout.

With two sensors, trigger and read them one at a time rather than simultaneously. A pause between measurements helps reduce **crosstalk**, where one sensor hears the other sensor's pulse.

## What the measurement can and cannot tell you

The sensor estimates distance within its acoustic beam. It does not produce an image, identify what the object is, or guarantee that every obstacle will reflect a usable echo. Test the actual mounting, target surfaces, and event environment.

The robot uses two HC-SR04-style sensors. Trigger them one at a time to reduce cross-interference. Sensor #1 uses GP10/GP11 and sensor #2 uses GP12/GP13; each Echo input has its own divider. See the [ultrasonic sensor electronics section](../electronics/README.md#ultrasonic-distance-sensors) and [Pico wiring guide](../wiring/pico_to_ultrasonic.md).

## Signal direction and voltage safety

TRIG is an input to the sensor: the Pico sends a 3.3 V pulse directly from GP10 or GP12. Echo travels in the opposite direction. The 5 V-powered HC-SR04 drives ECHO, which may be approximately 5 V, so it must pass through that sensor's own 1 kΩ/2 kΩ divider before reaching GP11 or GP13. Never connect raw Echo directly to Pico GPIO or share one divider between both sensors.
