# GPIO

**GPIO** means general-purpose input/output. A microcontroller GPIO pin can usually be configured as an **input**, which reads an electrical state, or an **output**, which produces a control state.

Digital states are described as **HIGH** and **LOW**. On the Pico, GPIO is based on 3.3 V logic: LOW is near ground and HIGH is near 3.3 V. These are logic levels, not general-purpose power outputs, and an input must stay within its safe voltage range.

GPIO current is limited because the pins are designed to exchange signals with electronic circuits. A motor needs much more current, especially when starting or stalled, and produces electrical noise. Connecting one directly to GPIO risks unreliable operation or permanent damage. GPIO should control the [L298N motor driver](../electronics/README.md#l298n-motor-controller), which switches motor current from the proper supply path.

See the [Pico pinout explanation](../electronics/README.md#raspberry-pi-pico) to distinguish physical header positions from the GPIO numbers used in MicroPython.

See [Pico to L298N wiring](../wiring/pico_to_l298n.md) and [digital inputs](digital_inputs.md).
