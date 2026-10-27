# Wiring the Pico to the L298N

Motor A is the left motor. Motor B is the right motor.

| Function | Pico GPIO | Physical pin | L298N connection |
|---|---:|---:|---|
| Left direction 1 | GP2 | 4 | IN1 |
| Left direction 2 | GP3 | 5 | IN2 |
| Left PWM/enable | GP4 | 6 | ENA |
| Right direction 1 | GP6 | 9 | IN3 |
| Right direction 2 | GP7 | 10 | IN4 |
| Right PWM/enable | GP8 | 11 | ENB |
| Common reference | Pico GND | Convenient GND pin | L298N GND |

L298N OUT1/OUT2 connect to the left motor. OUT3/OUT4 connect to the right motor. Do not label one input combination as universally physical “forward”; mounting and output-wire order determine the observed direction.

## Enable and regulator jumpers

If an ENA or ENB jumper permanently holds its channel HIGH, IN1–IN4 can still control direction and stopping, but the Pico cannot vary that channel's enable duty cycle. For PWM speed control, remove the relevant enable jumper, connect GP4 → ENA and GP8 → ENB, and generate PWM from the Pico.

The ENA jumper, ENB jumper, and separate **5V-EN/regulator jumper** are different. The first two affect motor-channel enable. The regulator jumper configures the final L298N 5 V rail used by the Pico and ultrasonic sensors.

## Power connections

The four-AA battery holder supplies the L298N motor input. The L298N `5V` terminal supplies Pico `VSYS` and both HC-SR04 VCC pins. Battery negative, L298N GND, Pico GND, and all sensor grounds join the common GND rail.

## Safe connection order

1. Remove batteries and disconnect USB.
2. Confirm the module labels and regulator-jumper position.
3. Remove the ENA and ENB jumpers when required for external PWM.
4. Connect common ground.
5. Connect IN1–IN4 and ENA/ENB using the table above.
6. Connect motors and the documented power wiring.
7. Complete the [pre-power check](../guides/pre_power_check.md) before applying power.

Never connect a motor to Pico GPIO or route motor current through the Pico. See [PWM](../concepts/pwm.md) and [full-system wiring](full_system_wiring.md).
