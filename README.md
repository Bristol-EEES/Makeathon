# BEEES Makeathon

Welcome to the official **BEEES Makeathon** repository.

This repository contains starter code, electronics documentation, guides, and example projects designed to help participants become familiar with the hardware and programming concepts used during the Makeathon.

The goal of these resources is **not to provide a complete competition solution**, but to give participants enough background to understand the basic structure of a robot and start experimenting before the event.

---

## What's in this Repository?

The repository will contain resources covering areas such as:

- Example line-following robot code
- Basic robot control
- Motor control
- Sensor interfacing
- Electronics and wiring documentation
- Microcontroller programming
- Example circuits
- Hardware setup guides
- Troubleshooting tips
- Useful reference material

Additional resources may be added as the Makeathon approaches.

---

## Example Line-Following Robot

A simple **line-following robot example** is included to demonstrate how sensor readings can be used to control a robot's motors.

The example is intended to introduce concepts such as:

1. Reading sensors
2. Processing sensor values
3. Making a control decision
4. Adjusting motor speeds
5. Repeating the process continuously

A typical control loop might look something like:

```text
Read Sensors
     ↓
Determine Position of Line
     ↓
Calculate Required Correction
     ↓
Adjust Left and Right Motor Speeds
     ↓
Repeat
```

The provided code should be treated as a **reference implementation**. Participants are encouraged to modify, experiment with, and improve the behaviour of their own robots.

---

## Electronics Documentation

The repository also contains electronics guides covering the basic hardware used during the Makeathon.

Topics may include:

- Microcontrollers
- Motors
- Motor drivers
- Line sensors
- Power systems
- Breadboards and prototyping
- Basic circuit design
- Wiring and connections
- Digital and analogue signals

These guides are intended to help participants who may have limited prior experience with electronics.

---

## Getting Started

Before the Makeathon, we recommend that you:

1. Look through the electronics documentation.
2. Familiarise yourself with the example line-following code.
3. Understand how the sensors and motors interact with the microcontroller.
4. Try modifying parts of the example code.
5. Make sure you understand the basic robot control loop.

You **do not need to memorise the code**. Focus on understanding what each part of the program is doing.

---

## Repository Structure

The repository may be organised approximately as follows:

```text
Makeathon/
│
├── examples/
│   └── line_follower/
│
├── electronics/
│   ├── sensors/
│   ├── motors/
│   ├── motor_drivers/
│   └── wiring/
│
├── guides/
│
├── docs/
│
└── README.md
```

The structure may change as additional resources are added.

---

## A Note for Beginners

Don't worry if you have never built a robot before.

The Makeathon is designed to be a practical learning experience, and the provided resources are intended to help you understand the fundamentals before you begin.

You are encouraged to:

- Experiment
- Ask questions
- Modify the example code
- Test different ideas
- Work with your teammates
- Learn through trial and error

Breaking things, debugging, and redesigning are all part of engineering.

---

## Important

The example code and documentation in this repository are provided as **learning resources**.

They are not intended to be copied directly as a finished Makeathon solution. Teams are encouraged to develop and improve their own designs during the event.

---

## BEEES

This repository is maintained by the **Bristol Electrical and Electronic Engineering Society (BEEES)** for the Makeathon.

Good luck, and have fun building! 🤖