7-Segment Countdown Timer
=========================

This project is a simple, hardware-driven countdown timer built for Arduino. It connects a physical push button to an analog pin and uses a single-digit 7-segment display to count down from 9 to 0. 

When you press and hold the button, the script registers the input, runs a stable 10-second sequence, and completely clears the display once the countdown finishes.

Core Features
------------
* Direct Segment Control: Uses individual pin assignments for each segment (A through G and the decimal point) to explicitly map and write the logic for numbers 0 to 9.
* Hardware Polling: Constantly checks the status of an analog pin waiting for a specific voltage spike (1023) to initiate the countdown sequence.
* Automated Countdown Loop: Executes a timed delay sequence that steps down through the digits at precise 1-second intervals.
* Clear Finish: Automatically triggers an 'off' state to clear the display at the end of the run, keeping the hardware idle until the next button press.

Hardware Setup
--------------
The project maps directly to standard digital IO pins, making it highly compatible with boards featuring extended pin layouts (like the Arduino Mega 2560).

Display Pin Mapping:
* Segment A  -> Pin 47
* Segment B  -> Pin 49
* Segment C  -> Pin 53
* Segment D  -> Pin 52
* Segment E  -> Pin 50
* Segment F  -> Pin 48
* Segment G  -> Pin 46
* Decimal Pt -> Pin 51

Input Mapping:
* Trigger Button -> Analog Pin A0

Note: Make sure to use current-limiting resistors on your segment lines to avoid burning out the display, and ensure your button setup provides a clean 5V (pulling the analog pin up to 1023) when pressed.

How to Use It
-------------
1. Open the project sketch in the Arduino IDE.
2. Connect your Arduino board to your computer and select your board type and COM port.
3. Upload the code.
4. Wire your 7-segment display and button according to the pin configuration above.
5. Press and hold the button connected to A0. The display will immediately show '9' and count down to '0' before turning off.
