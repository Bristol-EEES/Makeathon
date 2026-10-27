# Wiring the Motors to the L298N

The L298N has two output channels. **Motor A is the left motor** and connects to `OUT1`/`OUT2`. **Motor B is the right motor** and connects to `OUT3`/`OUT4`.

The [L298N reference diagram](../electronics/README.md#l298n-motor-controller) shows these common output labels. It is not a confirmed event wiring diagram, so the markings on the supplied module take priority.

The input pair for a channel selects the direction of current through its motor. Reversing the two output wires reverses that motor's physical rotation for the same control command.

## Test one motor at a time

1. Raise the wheels so the robot cannot drive away.
2. Use a low, controlled test command for the left motor (Motor A) while the right motor is stopped.
3. Check which wheel turns and in which physical direction.
4. Stop power before changing wires.
5. Repeat for the right motor (Motor B).

If one wheel turns backwards when both are commanded to move the robot forward, that motor may be wired with the opposite polarity. Swap only its two motor wires, or account for its orientation in the eventual control logic. Do not swap battery polarity.

See [motor direction](../concepts/motor_direction.md), [full-system wiring](full_system_wiring.md), the [electronics guide](../electronics/README.md), and the [pre-power check](../guides/pre_power_check.md).
