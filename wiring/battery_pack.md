# Wiring the Battery Pack

> Supplied battery chemistry, resulting voltage range, and the exact L298N power arrangement are to be confirmed.

> The final standalone power connection for the Raspberry Pi Pico is still to be confirmed. Follow the final Makeathon wiring diagram once published.

The battery pack's positive (`+`, commonly red) lead goes to the confirmed positive motor-supply terminal. Its negative (`-`, commonly black) lead goes to the motor-supply ground. That ground must connect to the control-system ground where required so the Pico and L298N share a signal reference.

This describes the motor-supply path only. It does not instruct you to connect the AA pack to the Pico or to `VSYS`.

Do not connect the battery by wire colour alone: verify the pack markings and terminal labels. If a multimeter is available, measure the pack with the batteries inserted and confirm both polarity and a plausible voltage before connection.

## Safety

- Switch off or remove the batteries before rewiring.
- Never allow the positive and negative leads to touch.
- Do not route motor power through a Pico GPIO pin or breadboard signal row.
- Check for stray wire strands and exposed conductors.
- Do not reverse the motor-supply polarity.
- Stop immediately if a wire, battery, or module becomes unexpectedly hot.

See [full-system wiring](full_system_wiring.md), the [electronics guide](../electronics/README.md), and the [pre-power check](../guides/pre_power_check.md).
