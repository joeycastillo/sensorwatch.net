---
title: "Settings"
linkTitle: "Settings"
weight: 100
---
The Settings watch face allows you to configure various options on your Sensor Watch. Like all other screens, you advance the field you’re setting with the Light button, and advance its value with the Alarm button. 

On the Classic LCD, the Settings watch face labels each setting with a two-letter code on the top row; on the custom LCD, you'll get a more descriptive line. The following list describes each setting and their options:

"CL" / "CLOCK" - Clock mode. This setting allows you to select a 12-or 24-hour clock display. All watch faces that support displaying the time will respect this setting; for example, both Clock, World Clock and Sunrise/Sunset will all display the time in a 24 hour format if the 24 hour clock is selected here.

"BT" / "BTN" - Button volume. The default option, "L", beeps the button softly, reserving louder beeps for alarms and countdown timers. Set the volume to "H" for high volume, or "N" to silence the buzzer entirely. Also note that a loud beep consumes significantly more power: one loud beep uses five times the power of a soft beep, which will impact your battery life after a while.

"TO" / "Tmout" - Timeout. Sets the time until screens that time out (like Settings and Time Set) snap back to the first screen. 60 seconds is a good default for the stock firmware, but if you choose a custom firmware with faces that you’d like to keep on screen for longer, you can set that here.

"LE" / "LoEne" - Low Energy mode. Sets the time until the watch enters its low energy sleep mode. Options range from 1 hour to 7 days, or Never. The more often Sensor Watch goes to sleep, the longer its battery will last — but you will lose the seconds indicator while it is asleep. This setting allows you to make a tradeoff between the device’s responsiveness and its longevity.

"LT" / "LED" - LED Backlight. This setting has three or four screens, depending on your hardware:

* The first screen lets you choose how long the LED should stay lit when the Light button is pressed. Options are "Instnt" to illuminate the LED only when the button is held down, "1 sec", "3 sec" and "5 sec", or “No LED” to disable the LED entirely.
* The remaining screens set the color intensity for the LEDs in your watch. Values range from 0 (off) to 15 (full intensity)

On a Lite or classic green board, you'll have two screens to set the green and red intensity; on a Pro board, you'll get screens for red, green and blue. Note that full intensity on all LEDs does not necessarily blend to white; a good starting point for a white backlight is values of 5, 10 and 15 for red, green and blue, respectively.
