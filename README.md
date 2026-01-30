<!-- PROJECT SHIELDS -->
![Repo Size](https://img.shields.io/github/repo-size/John-Valinsky/Windows)
![Last Commit](https://img.shields.io/github/last-commit/John-Valinsky/Windows)
![Open Issues](https://img.shields.io/github/issues/John-Valinsky/Windows)
![Stars](https://img.shields.io/github/stars/John-Valinsky/Windows)

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

void typeSlowly(const char* text, int delayMs) {
  for (int i = 0; text[i] != '\0'; i++) {
    DigiKeyboard.print(text[i]);
    DigiKeyboard.delay(delayMs); // Delay between each character
  }
}

void setup() {
  // Wait for PC to recognize Digispark
  DigiKeyboard.delay(2000);

  // Open Run dialog (Windows + R)
  DigiKeyboard.sendKeyPress(KEY_R, MOD_GUI_LEFT);
  DigiKeyboard.delay(500);

  // Type "notepad" and press Enter
  DigiKeyboard.print("notepad");
  DigiKeyboard.sendKeyPress(KEY_ENTER);

  // Wait for Notepad to open
  DigiKeyboard.delay(500);

  // Type message slowly
  typeSlowly("Congrats! Your Digispark is working!", 150); // 150ms per character
}

void loop() {
  // Nothing to do here
}

```
5 Click Verify.

6 Click Upload. The board will program after you plug it in.

7 Unplug it and plug it back in.

