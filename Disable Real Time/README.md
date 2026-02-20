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