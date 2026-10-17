# Understanding MicroPython

This page explains the MicroPython ideas needed to begin programming the Pico. For installing Thonny, connecting the board, and installing firmware, start with the [Pico and Thonny setup guide](pico_setup.md).

## What is MicroPython?

MicroPython is an implementation of Python designed for microcontrollers. A microcontroller has much less memory and storage than a desktop computer, but it can interact directly with electronic pins and other hardware.

MicroPython looks similar to desktop Python, so familiar statements such as this work:

```python
print("Hello")
```

However, the two environments are not identical:

- **Desktop Python** runs on the computer and has access to its operating system, files, and installed packages.
- **MicroPython** runs on the Pico and provides smaller, hardware-focused modules.

A package written for desktop Python may not be available in MicroPython. Conversely, MicroPython's hardware interfaces do not control the Pico if the code is accidentally run using the computer's desktop Python interpreter.

## Why use it on the Pico?

MicroPython provides a readable way to experiment with hardware without compiling a program after every edit. It is well suited to learning because commands can be tried interactively in the REPL and programs can be saved directly on the board.

## Hardware modules

MicroPython groups related features into **modules**. The `machine` module provides interfaces to microcontroller hardware. Importing one of its classes looks like this:

```python
from machine import Pin
```

This line only imports the `Pin` class; it does not select a GPIO or change any hardware.

### `Pin`, input, and output

A `Pin` object represents a microcontroller pin. A GPIO pin can be configured as:

- an **input**, which reads a digital HIGH or LOW signal; or
- an **output**, which produces a digital HIGH or LOW control signal.

Pico GPIO uses 3.3 V logic and can carry only small signal currents. It must not power a motor directly. See [GPIO](../concepts/gpio.md) for the electrical background.

### PWM

PWM (pulse-width modulation) switches an output rapidly. Changing the proportion of time spent on—the duty cycle—can control the average drive requested from suitable hardware such as a motor driver. See [PWM](../concepts/pwm.md) for a conceptual explanation.

### Timing

The `time` module provides delays and time-related functions. A short delay can make an experiment easier to observe, while timing inside a repeated control loop affects how often it reacts. Long blocking delays can prevent a program from responding promptly, so use timing deliberately.

## The REPL

The **REPL** is MicroPython's interactive prompt, shown as `>>>` in Thonny's Shell. REPL means read-evaluate-print loop: it reads a command, evaluates it, prints the result, and waits for another command.

The REPL is useful for confirming that Thonny is connected, trying one small statement at a time, reading error messages, and inspecting the board without first saving a file. Use Stop/Interrupt if a running program prevents the prompt from appearing.

## Files on the Pico

The Pico has a small filesystem used by MicroPython. A file saved there remains on the board after it is unplugged. This is different from saving the same file only on the computer.

Keep computer copies of important work. The Pico's filesystem is convenient for running code, but it should not be the only copy of a project.

## `main.py`

When MicroPython starts, a file named `main.py` on the Pico normally runs automatically. This makes it useful for a tested final program that should start when the robot is powered.

During experiments, use descriptive filenames and run them manually. Only create `main.py` when automatic startup is intended, because an error or infinite loop in it will run again after every restart.

Next: [uploading and saving code](uploading_code.md) · [Pico and Thonny setup](pico_setup.md)
