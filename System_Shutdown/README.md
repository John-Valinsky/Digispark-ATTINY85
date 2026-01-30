# Digispark Instant Shutdown (ATTiny85)

This Digispark (ATTiny85) script emulates a USB keyboard to instantly shut down a Windows machine by executing a shutdown command via the Run dialog.


# What This Script Does

## When the Digispark is plugged into a Windows system:

* Waits for the USB device to be recognized.

* Opens Run (Win + R).

* Types the command: shutdown -s -t 0

* Presses Enter.

* The system shuts down immediately.

After execution, the device enters an infinite loop and does nothing further.


# How It Works

* Uses the DigiKeyboard library

* Acts as a HID keyboard

* Requires no drivers on Windows

* Executes faster than a human can react