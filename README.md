
# BEEES Makeathon

Welcome to the official **BEEES Makeathon** repository.

This repository contains electronics documentation, setup guides, technical explanations, wiring references, and other resources designed to help participants understand the hardware used during the Makeathon.

The aim of these resources is to help you understand **how the components work, how they connect together, and how they can be used when building your robot**.

This repository does **not** provide a complete competition solution or finished line-following robot code. Designing and implementing your team's robot is part of the Makeathon challenge.

---

## What's in this Repository?

Resources will cover areas such as:

- Raspberry Pi Pico setup and usage
- Electronic components used during the Makeathon
- Motors and motor drivers
- Line sensors
- Power systems
- Wiring and connections
- GPIO, PWM and analogue/digital signals
- Basic robot control concepts
- Hardware setup
- Component datasheets and specifications
- Troubleshooting
- Useful reference material

Additional resources may be added as the Makeathon approaches.

---

## Getting Started

Before the Makeathon, we recommend becoming familiar with:

1. The Raspberry Pi Pico and its GPIO pins — start with the [Pico setup guide](guides/pico_setup.md)
2. The electronic components provided for the challenge
3. How the motors and motor driver work
4. How the line sensors detect the track
5. How the components should be wired together
6. Basic concepts such as PWM, digital inputs and analogue signals
7. The general control process used by a line-following robot

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

Topics may include:

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

For each component, the documentation will aim to explain:

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
│   ├── pico_to_l298n.md
│   ├── motors_to_l298n.md
│   ├── battery_pack.md
│   └── full_system_wiring.md
│
├── concepts/
│   ├── gpio.md
│   ├── pwm.md
│   ├── digital_inputs.md
│   ├── motor_direction.md
│   └── line_following_basics.md
│
├── guides/
│   ├── pico_setup.md          # Thonny installation and connecting the board
│   ├── micropython_setup.md   # Understanding and configuring MicroPython
│   ├── uploading_code.md      # Run, save, and main.py workflow
│   └── pre_power_check.md
│
├── troubleshooting/
│   └── README.md
│
├── assets/
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
