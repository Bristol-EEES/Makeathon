# Wiring the Motors to the L298N

The L298N has two output channels. **Motor A is the left motor** and connects to `OUT1`/`OUT2`. **Motor B is the right motor** and connects to `OUT3`/`OUT4`.

The [L298N reference diagram](../electronics/README.md#l298n-motor-controller) shows these common output labels. It is not a confirmed event wiring diagram, so the markings on the supplied module take priority.

The input pair for a channel selects the direction of current through its motor. Reversing the two output wires reverses that motor's physical rotation for the same control command.

## Motor direction calibration

Complete this before debugging line-following behaviour:

1. Check the documented power and common-ground connections.
2. Raise the drive wheels so the robot cannot move away.
3. Test Motor A by itself and record which way its wheel rotates.
4. Test the opposite IN1/IN2 state and identify which state produces physical forward motion.
5. Stop Motor A and repeat the process for Motor B using IN3/IN4.
6. Command both motors in their intended physical-forward states.
7. Confirm that both wheels would propel the robot forward.
8. If one wheel is reversed, disconnect battery and USB power, swap only that motor's two L298N output wires, and retest. Alternatively, invert that motor's direction states in your own code.
9. Test each enable channel at a high PWM duty so the motor starts reliably, then reduce it gradually to find the useful running range.
10. Only after both motors behave predictably should you begin integrating sensor behaviour.

Motor A uses OUT1/OUT2 and Motor B uses OUT3/OUT4. Never swap battery polarity to correct one motor. Physical direction calibration is a normal assembly step, not evidence that the reference GPIO table is wrong.

See [motor direction](../concepts/motor_direction.md), [full-system wiring](full_system_wiring.md), the [electronics guide](../electronics/README.md), and the [pre-power check](../guides/pre_power_check.md).
