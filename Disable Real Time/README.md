# Windows Real-Time Protection Toggle (Digispark)

This project demonstrates how a Digispark / DigiKeyboard (USB HID) device can automate keyboard input on Windows to navigate the Windows Security interface and toggle Real-Time Protection.

It’s essentially a proof-of-concept showing how HID devices can interact with OS security settings through simulated keystrokes.


# What This Does

* Registers as a USB keyboard (HID).

* Opens the Start Menu.

* Launches Windows Security.

* Navigates through the UI using keystrokes.

* Toggles Real-Time Protection ON or OFF (depending on current state).

There is no malware, payload execution, persistence, or network activity involved — just keystroke automation.


# Why This Exists

* Learning how USB HID attacks work at a conceptual level.

* Understanding why physical access = full access.

* Red-team / blue-team demonstrations.

* Security awareness training.

* Digispark / DigiKeyboard experimentation.


# Requirements

Hardware

* Digispark ATtiny85 (or compatible).

* USB port on a Windows machine.

Software

* Arduino IDE.

* Digispark board definitions.

* DigiKeyboard library.

* Windows (tested on Windows 10 / 11).


# Warnings

* Physical access required — this does NOT work remotely.

* Fragile by design — small UI changes can break it.

* May fail silently if timing or focus changes.

* Requires admin privileges on the target system.

* Disabling Real-Time Protection reduces system security.

Do NOT use on machines you don’t own or have explicit permission to test.


# Defensive Takeaways

* Lock your screen when away.

* Disable unknown USB devices.

* Use device control / USB whitelisting.

* Monitor Defender tampering events.

* Require admin approval for security changes.


# Tested Environment

* Windows 10 / 11 (English UI).

* Default Windows Security layout.

* Digispark ATtiny85 @ 16.5 MHz.


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