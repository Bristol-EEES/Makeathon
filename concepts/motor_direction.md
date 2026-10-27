# Motor Direction

A DC motor's direction depends on the polarity across its two terminals. An **H-bridge** reverses that polarity electronically, allowing a controller to request forward or reverse motion without moving wires.

For one enabled L298N motor channel:

| Input 1 | Input 2 | Behaviour |
|---|---|---|
| LOW | LOW | Brake / stop |
| HIGH | LOW | Direction A |
| LOW | HIGH | Direction B |
| HIGH | HIGH | Brake / stop |

If the enable input is LOW, the channel is disabled and the motor normally coasts instead of being actively braked. GP4 controls ENA for the left motor and GP8 controls ENB for the right motor. Remove their enable jumpers if those jumpers permanently hold ENA/ENB HIGH.

Direction A and Direction B are opposite rotations, not universal labels for forward and reverse. Physical forward depends on how the motor is mounted and which way its two wires are connected. Swapping those two wires swaps the physical directions.

> Electrical direction is defined by the L298N input state. Physical forward or backward depends on motor mounting and wiring polarity.

## Motor spins the wrong way

The L298N cannot know which rotation will move an assembled robot physically forward. Gearbox orientation, left/right mechanical symmetry, motor mounting, and the order of the two motor wires can all reverse the observed motion. Two channels given apparently similar direction states can therefore make the robot spin instead of travelling forward. This does not by itself mean that the Pico, L298N, or program is broken.

There are two valid corrections:

### Swap that motor's output wires

With **battery and USB power disconnected**, swap only the two wires belonging to the reversed motor. For example, change wire A → OUT1 and wire B → OUT2 into wire A → OUT2 and wire B → OUT1. Never reverse the battery polarity and do not disturb the other motor's wires.

For a beginner build, this is often the simplest way to make both motors follow the same software direction convention.

### Reverse that motor's software state

Alternatively, reverse the HIGH/LOW values used for that motor. For example, replace:

```python
in1.value(1)
in2.value(0)
```

with:

```python
in1.value(0)
in2.value(1)
```

Either approach is acceptable. Test and record the actual result instead of assuming Direction A is physical forward.

The robot uses **differential drive**: changing the relative direction or speed of the left and right wheels makes it travel straight, curve, or turn. Because the motors are mounted as mirror images, the same electrical polarity may make one wheel drive the robot forward and the other backward. Establish the physical direction of each motor with an individual test.

The left direction inputs are GP2/GP3 → IN1/IN2. The right direction inputs are GP6/GP7 → IN3/IN4. See [motors to L298N](../wiring/motors_to_l298n.md) and the [L298N overview](../electronics/README.md#l298n-motor-controller).
