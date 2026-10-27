
# BEEES Makeathon

Welcome to the official **BEEES Makeathon** repository.

This repository contains electronics documentation, setup guides, technical explanations, wiring references, and other resources designed to help participants understand the hardware used during the Makeathon.

The aim of these resources is to help you understand **how the components work, how they connect together, and how they can be used when building your robot**.

This repository does **not** provide a complete competition solution or finished line-following robot code. Designing and implementing your team's robot is part of the Makeathon challenge.

---

## Hardware Provided

Each team will receive:

- 1× Raspberry Pi Pico
- 2× DC motors with wheels
- 2× IR line sensor modules
- 2× HC-SR04 ultrasonic sensors
- 1× L298N motor controller
- 1× breadboard
- 1× 4×AA battery holder
- 4× AA batteries
- 2× 1 kΩ resistors
- 2× 2 kΩ resistors

The four resistors form two separate HC-SR04 Echo voltage dividers: one 1 kΩ and one 2 kΩ resistor for each sensor. They protect Pico GPIO signal inputs; they are not used to power the Pico.

See the [Electronics Guide](electronics/README.md) for an explanation of each component and its role in the robot.

---

## What's in this Repository?

Resources cover areas such as:

- Raspberry Pi Pico setup and usage
- Electronic components used during the Makeathon
- Motors and motor drivers
- Line sensors
- Ultrasonic distance sensors
- Power systems
- Wiring and connections
- GPIO, PWM and analogue/digital signals
- Basic robot control concepts
- Hardware setup
- Component datasheets and specifications
- Troubleshooting
- Useful reference material

---

## Getting Started

Build and test one subsystem at a time. This order gives beginners a clear path without jumping straight to a complete robot program:

1. [Install Thonny, connect the Pico, install MicroPython, and run the REPL test](guides/pico_setup.md).
2. Learn the difference between [GPIO numbers and physical pins](concepts/gpio.md).
3. [Connect and calibrate both IR sensors](guides/ir_sensor_calibration.md), then run their isolated input test.
4. Read about [motor direction](concepts/motor_direction.md), wire the [Pico to the L298N](wiring/pico_to_l298n.md), and test the left and right motors separately.
5. Learn how [PWM controls the motor-enable command](concepts/pwm.md) and try the isolated PWM example in the [electronics guide](electronics/README.md#motor-speed-with-pwm).
6. Wire and test [ultrasonic sensor #1, then sensor #2](wiring/pico_to_ultrasonic.md).
7. Compare the assembled robot with the [final diagram and connection tables](wiring/full_system_wiring.md).
8. Complete the [pre-power check](guides/pre_power_check.md).
9. Read the [line-following concepts](concepts/line_following_basics.md), then begin developing and testing your team's own control logic.

You do **not** need to have built a line-following robot before the event.

The purpose of this documentation is to give you the background needed to understand the hardware and start developing your own solution during the Makeathon.

---

## How a Line-Following Robot Works

At a high level, a line-following robot repeatedly performs a simple process:

```text
Read Sensors
     ↓
Determine Where the Line Is
     ↓
Decide How the Robot Should Respond
     ↓
Control the Motors
     ↓
Repeat
```

The sensors provide information about the robot's position relative to the line.

Your program must then use this information to decide how the motors should respond.

Exactly **how you implement this behaviour is up to your team**.

---

## Electronics Documentation

The electronics documentation explains the hardware provided during the Makeathon.

Topics include:

- Raspberry Pi Pico
- DC motors
- Motor drivers
- Line sensors
- Batteries and power
- Wiring and connections
- GPIO
- PWM
- Analogue and digital signals
- Basic electrical concepts

For each component, the documentation explains:

- What the component is
- What it does
- How it works
- Important electrical specifications
- How to connect it
- How it interacts with the rest of the robot
- Common problems and troubleshooting steps

---

## Repository Structure

The repository documentation is organised as follows:

```text
Makeathon/
│
├── electronics/
│   └── README.md
│
├── wiring/
│   ├── pico_to_ir_sensors.md
│   ├── pico_to_ultrasonic.md
│   ├── pico_to_l298n.md
│   ├── motors_to_l298n.md
│   ├── battery_pack.md
│   └── full_system_wiring.md
│
├── concepts/
│   ├── gpio.md
│   ├── pwm.md
│   ├── digital_inputs.md
│   ├── ultrasonic_distance.md
│   ├── motor_direction.md
│   └── line_following_basics.md
│
├── guides/
│   ├── pico_setup.md          # Thonny installation and connecting the board
│   ├── micropython_setup.md   # Understanding and configuring MicroPython
│   ├── uploading_code.md      # Run, save, and main.py workflow
│   ├── ir_sensor_calibration.md
│   └── pre_power_check.md
│
├── troubleshooting/
│   └── README.md
│
├── assets/
│   ├── README.md
│   ├── diagrams/
│   └── images/
│
└── README.md
```

---

## For Beginners

No previous robotics experience is required.

The Makeathon is intended to be a practical engineering challenge and learning experience.

You are encouraged to:

- Read through the documentation
- Ask questions
- Experiment with the hardware
- Test your ideas
- Debug problems
- Work with your teammates
- Try different approaches

Understanding why something does not work is often just as useful as getting it working the first time.

---

## Important

The resources in this repository are intended to help you **understand the hardware and engineering concepts involved in the challenge**.

They are not intended to provide a finished robot or a copy-and-paste competition solution.

Teams are expected to develop and implement their own solution during the Makeathon.

---

## BEEES

This repository is maintained by the **Bristol Electrical and Electronic Engineering Society (BEEES)** for the Makeathon.

Good luck, and have fun building! 🤖

Image sources and reuse information are tracked in the [asset credits](assets/README.md).
