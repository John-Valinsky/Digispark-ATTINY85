# Digispark-ATTINY85

This repository contains code and resources for projects using the Digispark ATTINY85 microcontroller. The Digispark is a compact, Arduino-compatible board ideal for small, low-power applications.

# Features

* Arduino-compatible ATTINY85 development

* USB interface for easy programming

* Compact and low-cost for hobbyist projects

# Getting Started

1 Install the Arduino IDE
```bash
https://www.arduino.cc/en/software/
```
2 Add Digispark boards via File → Preferences → Additional Boards Manager URLs
```bash
https://raw.githubusercontent.com/digistump/arduino-boards-index/master/package_digistump_index.json
```
3 Open the project sketch and select Digispark (Default - 16.5 MHz) as the board.

4 Copy this code for testing
```bash
#include <DigiKeyboard.h>

void setup() {
  // Give the PC a moment to recognize the Digispark
  DigiKeyboard.delay(2000);

  // Open Run dialog (Windows + R)
  DigiKeyboard.sendKeyPress(KEY_R, MOD_GUI_LEFT); // MOD_GUI_LEFT is the Windows key
  DigiKeyboard.delay(500);

  // Type "notepad"
  DigiKeyboard.print("notepad");
  DigiKeyboard.delay(200);

  // Press Enter to open Notepad
  DigiKeyboard.sendKeyPress(KEY_ENTER);
}

void loop() {
  // Nothing to do here
}
```
5 Click Upload. The board will program after you plug it in.

