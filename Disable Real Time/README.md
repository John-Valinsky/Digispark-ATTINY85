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