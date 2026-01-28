# Digispark Mouse Jiggler

A simple USB HID mouse jiggler built using a Digispark (ATtiny85).
This project periodically moves the mouse pointer in random intervals to prevent systems from going idle, locking, or activating screen savers.

Originally written by James Franklin for Air-Gap in 2019.


# Features

* Emulates a USB mouse using DigiMouse.

* Randomized delay between movements.

* Small, cheap, and stealthy hardware.

* No drives required.

* LED activity indicator via GPIO pin.


# Hardware Required

* Digispark ATtiny85.

* USB port.


# Software Requirements

* Arduino IDE.

* Digispark board support installed.

* DigiMouse library.


# Required Library

* DigiMouse


# Configuration

You can adjust the random delay between mouse movements using these variables:

```bash
unsigned int LowerCycleTime = 500;   // Minimum delay (ms)
unsigned int UpperCycleTime = 1000;  // Maximum delay (ms)
```
* Default range: 0.5 - 1 second

* Max supported value: 65535 ms


# How it works

* On startup, the device seeds randomness using analog noise.

* The mouse is moved in X and Y directions repeatedly.

* Each movement:

  1 Toggles GPIO pin 1 (LED indicator).

  2 Sends large relative mouse movements.

  3 Waits a random delay before the next action.

* Loop repeats indefinitely.

The randomized timing helps avoid detection by simple activity monitors.


# Usage

* Flash the sketch to your Digispark.

* 