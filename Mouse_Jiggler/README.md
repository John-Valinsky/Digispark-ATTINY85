<!-- PROJECT SHIELDS -->
![Repo Size](https://img.shields.io/github/repo-size/John-Valinsky/Windows)
![Last Commit](https://img.shields.io/github/last-commit/John-Valinsky/Windows)
![Open Issues](https://img.shields.io/github/issues/John-Valinsky/Windows)
![Stars](https://img.shields.io/github/stars/John-Valinsky/Windows)

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


# Codes
```bash
// Digispark Mouse Jiggler
// Original version is Written by James Franklin for Air-Gap in 2019
// www.air-gap.com.au

#include <DigiMouse.h>
unsigned int LowerCycleTime = 500; //Minimum Time in milli-seconds between each mouse action  Default: 10000 (10 Seconds), Max 65535ms
unsigned int UpperCycleTime = 1000; //Maximum Time in milli-seconds between each mouse action  Default: 30000 (30 Seconds), Max 65535ms
//Random Function will randomly execute a mouse move between these two values
void setup() {
  randomSeed(analogRead(0));  //Random Seed off background noise on analog pin
  pinMode(1, OUTPUT);
  DigiMouse.begin(); //start

}
 void loop() {
  // Moves mouse 1 pixel in the X and Y directions (up, down, left, or right) in a loop

  // Move up
  digitalWrite(1, HIGH);
  DigiMouse.moveY(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move down
  digitalWrite(1, HIGH);
  DigiMouse.moveY(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move left
  digitalWrite(1, HIGH);
  DigiMouse.moveX(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move right
  digitalWrite(1, HIGH);
  DigiMouse.moveX(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move right
  digitalWrite(1, HIGH);
  DigiMouse.moveX(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));
  
// Move left
  digitalWrite(1, HIGH);
  DigiMouse.moveX(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

   // Move down
  digitalWrite(1, HIGH);
  DigiMouse.moveY(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move up
  digitalWrite(1, HIGH);
  DigiMouse.moveY(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move left
  digitalWrite(1, HIGH);
  DigiMouse.moveX(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move right
  digitalWrite(1, HIGH);
  DigiMouse.moveX(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));

  // Move right
  digitalWrite(1, HIGH);
  DigiMouse.moveX(1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));
  
// Move left
  digitalWrite(1, HIGH);
  DigiMouse.moveX(-1000000);
  DigiMouse.delay(50);
  digitalWrite(1, LOW);
  DigiMouse.delay(random(LowerCycleTime, UpperCycleTime));
}
```

# Usage

* Flash the sketch to your Digispark.

* Plug it into a USB port.

* The system will detect it as a standard mouse.

* Mouse movement begins automatically.

  No user interaction required.


# Notes & Warnings

* This device actively moves your mouse — do not use during precise tasks.

* Intended for educational and personal use.

* Use responsibly and in accordance with workplace policies.


# License

Free for personal and educational use.
Original credit must be retained.