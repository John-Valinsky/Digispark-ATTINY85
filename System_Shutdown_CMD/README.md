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