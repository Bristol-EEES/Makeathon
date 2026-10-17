# Motor Direction

A DC motor's direction depends on the polarity across its two terminals. An **H-bridge** reverses that polarity electronically, allowing a controller to request forward or reverse motion without moving wires.

For one conceptual motor channel:

| Direction input 1 | Direction input 2 | Typical result |
|---|---|---|
| LOW | LOW | Stop/coast, depending on driver configuration |
| HIGH | LOW | One direction |
| LOW | HIGH | Opposite direction |
| HIGH | HIGH | Stop/brake, depending on driver configuration |

Confirm the behaviour of the supplied module; the table does not assign Pico pins.

The robot uses **differential drive**: changing the relative direction or speed of the left and right wheels makes it travel straight, curve, or turn. Because the motors are mounted as mirror images, the same electrical polarity may make one wheel drive the robot forward and the other backward. Establish the physical direction of each motor with an individual test.

See [motors to L298N](../wiring/motors_to_l298n.md) and the [L298N overview](../electronics/README.md#l298n-motor-controller).
