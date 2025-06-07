---
title: "Countdown"
linkTitle: "Countdown"
weight: 60
---
This watch face implements a simple countdown timer with one-second resolution:

* Long press the ALARM button to enter setting mode and adjust the countdown timer. 
    * In this mode, pressing ALARM advances the hour, minute or second.
    * Pressing LIGHT advances to the next field.
    * A long press on LIGHT clears curent field and any after it.
* Press the ALARM button to start and pause the countdown, similar to the stopwatch face.
* When paused or stopped, press the LIGHT button to reset the countdown.

Max countdown is 23 hours, 59 minutes and 59 seconds.

If you have the [accelerometer sensor](/docs/sensorboards/accelerometer) installed, this watch face will enable tap detection for three seconds when the face comes on screen. You can tap the watch to increment the number of minutes you want to count, and each tap will extend tap detection for another three seconds. Tap detection will be disabled after this timeout, or when the wearer presses the ALARM button to start the timer. This "quick set" time will not be remembered; when reset, the countdown timer will be reset to the last _manually entered_ countdown time
