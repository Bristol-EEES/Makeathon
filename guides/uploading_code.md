# Getting Your Code onto the Pico

Complete the [Pico and Thonny setup guide](pico_setup.md) first. These steps assume Thonny can already reach the Pico's MicroPython REPL.

## Method 1 — Run Directly from Thonny

This is the fastest method while experimenting.

1. Connect the Pico with a USB data cable.
2. In Thonny, select **MicroPython (Raspberry Pi Pico)**, or the closest option for the exact model, and choose its USB/serial port.
3. Open an existing `.py` file or create a new one.
4. Press the green Run button or use Thonny's Run command.
5. Observe output and errors in the Shell.
6. Use Stop/Interrupt before making hardware changes.

Running an unsaved editor file can send it to the interpreter temporarily. It does not necessarily mean that the file has been stored on the Pico.

## Method 2 — Save the File onto the Pico

1. Connect the Pico and select its MicroPython interpreter.
2. Open or create the program in Thonny.
3. Choose **Save As** from the File menu, or use the equivalent save command in your Thonny version.
4. When asked for a location, choose **Raspberry Pi Pico**, not only the computer.
5. Enter a descriptive filename ending in `.py`.
6. Save the file, then run it and check the Shell.

Files saved this way are stored on the board's MicroPython filesystem. Keep a separate copy on the computer as a backup.

## Running Automatically at Startup

A file named `main.py` on the Pico normally runs when MicroPython boots. Use that name only for a program you have tested and intentionally want to start automatically.

While developing, names such as `hello.py` or `experiment.py` make files easier to distinguish. If `main.py` contains an error or infinite loop, use Stop/Interrupt immediately after connecting to regain access to the REPL.

## Is the Code on the Pico or Only on the Computer?

Look at where Thonny says the file is stored:

- A normal computer path means the file is on the computer.
- A device/Pico location means the file is on the Pico.
- If a program runs but no saved Pico file is visible, Thonny may only have sent the editor contents for that run.

A simple check is to stop the program, close its editor tab, and use Thonny's device file browser or Open command to inspect files on the Raspberry Pi Pico. Do not assume that pressing Run also saved the file.

## Common Thonny Connection Problems

| Problem | Simple recovery step |
|---|---|
| Pico does not appear | Reconnect it, try another USB port, and use a known data-capable cable. |
| Wrong interpreter selected | Select MicroPython for the exact Raspberry Pi Pico model, not desktop Python 3. |
| Wrong serial or COM port | Choose the port that appears when the Pico is connected; disconnect/reconnect to identify it. |
| Charge-only USB cable | Replace it with a cable known to transfer files or data. |
| MicroPython is not installed | Use Thonny's MicroPython firmware installer or follow the BOOTSEL recovery in the setup guide. |
| Pico keeps running old code | Press Stop/Interrupt, inspect files stored on the Pico, and check whether an old `main.py` starts automatically. |
| Shell says the device is busy | Stop the running program, wait briefly, and restart the interpreter if needed. |
| Connection was interrupted | Stop, reconnect the USB cable, reselect the Pico interpreter/port, and run again. |
| `main.py` immediately enters an infinite loop | Press Stop/Interrupt soon after reconnecting; then rename, edit, or remove the faulty startup file. |
| Another program owns the serial port | Close other editors, terminal programs, and serial monitors that may be connected to the Pico, then reconnect in Thonny. |

For a difficult connection problem, disconnect the robot's other power sources, put the Pico into BOOTSEL mode, and reinstall the correct stable MicroPython firmware for the exact board model. This replaces firmware, so use it as a recovery step rather than repeating it for ordinary code edits.

See [Pico and Thonny setup](pico_setup.md), [understanding MicroPython](micropython_setup.md), and [troubleshooting](../troubleshooting/README.md).
