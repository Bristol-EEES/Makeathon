# Motor Direction

A DC motor's direction depends on the polarity across its two terminals. An **H-bridge** reverses that polarity electronically, allowing a controller to request forward or reverse motion without moving wires.

For one enabled L298N motor channel:

| Input 1 | Input 2 | Behaviour |
|---|---|---|
| LOW | LOW | Brake / stop |
| HIGH | LOW | Direction A |
| LOW | HIGH | Direction B |
| HIGH | HIGH | Brake / stop |

If the enable input is LOW, the channel is disabled and the motor normally coasts instead of being actively braked. Confirm the supplied module's enable-jumper arrangement; the table does not assign Pico pins.

Direction A and Direction B are opposite rotations, not universal labels for forward and reverse. Physical forward depends on how the motor is mounted and which way its two wires are connected. Swapping those two wires swaps the physical directions.

The robot uses **differential drive**: changing the relative direction or speed of the left and right wheels makes it travel straight, curve, or turn. Because the motors are mounted as mirror images, the same electrical polarity may make one wheel drive the robot forward and the other backward. Establish the physical direction of each motor with an individual test.

See [motors to L298N](../wiring/motors_to_l298n.md) and the [L298N overview](../electronics/README.md#l298n-motor-controller).
