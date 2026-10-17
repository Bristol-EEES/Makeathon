# Pre-Power Check

Complete this check before inserting batteries or switching on motor power. If anything is uncertain, keep power off and ask a supervisor.

- [ ] Battery positive and negative match the confirmed motor-supply terminals.
- [ ] No visible short connects positive power directly to ground.
- [ ] Pico, sensor, and motor-driver grounds are connected where required by the design.
- [ ] Each motor connects to a pair of motor-driver outputs, not to Pico GPIO.
- [ ] Motor power does not pass through a GPIO pin or signal connection.
- [ ] Sensor VCC, GND, and output pins match the confirmed sensor pinout.
- [ ] Sensor output voltage is safe for 3.3 V Pico GPIO.
- [ ] Breadboard power rails are correctly identified; any split rails are bridged only where intended.
- [ ] No loose wires can fall into another terminal or touch a wheel.
- [ ] No exposed conductors or stray wire strands can cause a short.
- [ ] L298N terminals and jumpers match the supplied module's confirmed arrangement.
- [ ] Batteries are inserted with the orientation marked on the holder.
- [ ] The robot is raised or restrained for its first motor test.

Use the [full-system wiring guide](../wiring/full_system_wiring.md) during inspection. If a check fails, disconnect power before making changes.
