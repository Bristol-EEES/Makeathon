# Troubleshooting

Switch off motor power before changing wiring. Work through one subsystem at a time, and ask a supervisor if a component becomes hot, smells unusual, or appears damaged.

| Symptom | Possible Cause | What to Check |
|---|---|---|
| Pico not detected by computer | Charge-only USB cable, wrong port, driver/editor issue, or firmware missing | Try a known data cable and another port; confirm the interpreter/device; use the [Pico setup guide](../guides/pico_setup.md) if firmware recovery is needed. |
| Pico does not appear in Thonny | Wrong interpreter or port, charge-only USB cable, or missing firmware | Check the cable, select the Pico's MicroPython interpreter and USB/serial port, then reconnect. |
| `RPI-RP2` appears but code will not run | The Pico is in BOOTSEL firmware mode rather than normal MicroPython mode | Install the correct firmware if needed, allow the board to reboot, then reconnect normally without holding BOOTSEL. |
| Code runs on the computer instead of the Pico | Desktop Python interpreter is selected | Select **MicroPython (Raspberry Pi Pico)**, or the closest option for the exact board, and its port. |
| Thonny says the device is busy | A program is still running, or another application has locked the serial connection | Press Stop/Interrupt; close other serial tools; restart Thonny's interpreter and reconnect if necessary. |
| Changes do not appear after restart | The edited file was saved only on the computer, or a different Pico file is running | Inspect the files stored on the Pico and check where Thonny saved the `.py` file. |
| Program does not start after unplugging USB | The file is not stored on the Pico as `main.py`, or the Pico lacks the intended independent power path | Check the filename and save location. Do not guess at power wiring; follow the confirmed wiring guide. |
| Code will not run | Syntax/runtime error, wrong interpreter, board busy, or problematic `main.py` | Read the first shell error; select MicroPython and the Pico; press Stop/Interrupt; restart and test a minimal non-robot program. |
| Sensor always reads the same value | Incorrect VCC/GND/output wiring, unsuitable threshold, wrong height, or no common ground | Confirm the module pin labels and safe supply, then follow the [IR sensor calibration guide](../guides/ir_sensor_calibration.md) over both surfaces. |
| Sensor reacts backwards | Module output sense differs from the assumption, or light/dark surfaces are reversed | Use the [calibration procedure](../guides/ir_sensor_calibration.md) to record the actual HIGH/LOW state over line and background; adapt your interpretation rather than rewiring power. |
| Sensor reading is unstable | Sensor is near its threshold, mounting height is changing, ambient light is varying, or wiring is loose | Secure the mounting and wiring, then recalibrate under lighting similar to the event conditions. |
| The two sensors behave differently | Their mounting, threshold settings, or component tolerances differ | Calibrate each sensor separately at its intended height using the [IR sensor calibration guide](../guides/ir_sensor_calibration.md). |
| Ultrasonic sensor always times out | Incorrect Trig/Echo wiring, missing common ground, unsafe/missing level conditioning, or no usable echo | Power off and compare VCC, Trig, Echo, and GND with the [ultrasonic wiring guide](../wiring/pico_to_ultrasonic_sensors.md); then test one sensor facing a large solid object. |
| Ultrasonic distance jumps or is unrealistic | Angled, soft, small, or moving target; loose mounting; reflections; or readings taken too quickly | Secure the sensor, face a large flat target, add time between readings, and compare several measurements. |
| Two ultrasonic sensors interfere with each other | Both modules transmit at the same time and one receives the other's echo | Trigger and finish reading one module before triggering the other; leave a short pause between measurements. |
| Ultrasonic sensor works but Pico becomes unreliable | Echo may be exceeding the Pico's 3.3 V GPIO range | Disconnect power immediately and confirm the approved Echo voltage divider or level shifter before reconnecting. |
| Motor does not move | No motor supply, disabled channel, loose output wire, stalled mechanism, or wrong control state | Power off; inspect battery and motor-output wiring; confirm the channel enable arrangement; test that motor individually with wheels clear. |
| Only one motor moves | One channel is disabled, one connection is loose, or control signals target the wrong channel | Compare both channels systematically; swap tests only with power off; verify IN and EN labels on the supplied module. |
| Motor moves in the wrong direction | Motor leads are reversed relative to the intended physical direction | Identify that motor, power off, then swap its two output wires or account for its mounting in your own control logic. Never reverse the battery. |
| Motors behave inconsistently | Weak batteries, loose connections, mechanical rubbing, electrical noise, or overly high load | Check battery condition, terminals, common ground, wheel freedom, and whether behaviour changes when each motor is tested alone. |
| Pico resets or disconnects when motors start | Battery sag, poor grounding, electrical noise, or motor current entering the control-power path | Stop; check the power architecture and common ground, tighten connections, and ask a supervisor to review the supply arrangement. Do not bypass protection or guess at new power links. |
| Robot turns the wrong way | Left/right motors or sensors are confused, or one motor's physical forward direction differs | Label each sensor and motor; test each independently; write down actual directions before combining the system. |
| Breadboard circuit appears unpowered | Split rail, wrong row, reversed rails, or missing ground | Use the board markings; check whether rails are split; trace power and ground one connection at a time with power off. |

Return to the [electronics guide](../electronics/README.md), [full-system wiring](../wiring/full_system_wiring.md), or [pre-power check](../guides/pre_power_check.md).
