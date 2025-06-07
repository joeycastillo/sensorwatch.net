---
title: "Prebuilt Alternative Firmware for Sensor Watch"
linkTitle: "Prebuilt Alternative Firmware for Sensor Watch"
weight: 20
---
As part of the move to Second Movement, we are paring down the number of alternative firmware images available on this page. Soon an online watch face builder will make it easier to build your own firmware, tailored to your device, with just the watch faces you want to make use of. In the meantime, we are offering two firmware images: the standard Movement firmware image, and an alternative version that supports experimentation with activity tracking.

Select the firmware image that matches both the color of your Sensor Watch board and the display you are using. Note that unless you bought a custom LCD from Crowd Supply, and swapped it out for the original Casio LCD that came with your wristwatch, you probably want to download variant 1: Original Casio display. Plug your board into a USB Micro-B cable, double tap the Reset button (the LED should pulse in red), and drag the new firmware over to the WATCHBOOT drive.

If you drag over the wrong color of firmware, i.e. if you put the blue/green firmware onto a red board, or the red firmware onto a Pro board, the LED will likely light up in yellow or white before you even unplug the board. This indicates an error; if this happens, double tap Reset, and drag the correct firmware onto your board.

If you drag over the wrong display variant, i.e. a Classic display when you have the custom LCD or vice versa, the display will appear garbled and unreadable when assembled. Disassemble the watch and repeat the above steps with the correct firmware image.

Note that all of these firmware images have the "Preferences" and "Time Set" screens hidden behind a long press of the Mode button from the Clock display. To set the time or change your settings, you must long-press the Mode button once, and then press it a few more times until you reach those screens.

* [Second Movement Standard Edition](#second-movement-standard-edition)
* [Second Movement Activity Explorer](#second-movement-activity-explorer)

Second Movement Standard Edition
--------------------------------

**Optional Sensor Boards:** Temperature Sensor, Motion Sensor

This is the standard firmware for Second Movement.

* Sensor Watch Lite
    1. [Original Casio display](/docs/firmware/download/standard_red_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_red_custom.uf2)
* Sensor Watch Pro
    1. [Original Casio display](/docs/firmware/download/standard_pro_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_pro_custom.uf2)
* Sensor Watch Classic (green boards)
    1. [Original Casio display](/docs/firmware/download/standard_green_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_green_custom.uf2)
* Limited Edition Sensor Watch (blue boards)
    1. [Original Casio display](/docs/firmware/download/standard_blue_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_blue_custom.uf2)

This firmware image contains the following watch faces: 

* Simple Clock - A basic clock with date for timekeeping. Long press ALARM to toggle hourly chime.
* World Clock - Long press ALARM to configure with a custom two- or three-letter title and time zone.
* Sunrise/Sunset - Local sunrise and sunset times. (Press Alarm to see the next sunrise / sunset)
* Moon Phase - Today's moon phase. (press Alarm to see days in the future, if you want to know i.e. the next full moon)
* Stopwatch (by Wesley Ellis) - A stopwatch with one-second resolution.
* Countdown (by Wesley Ellis) - A countdown timer.
* Alarm (by Josh Berson) - A simple alarm that fires daily at the same time.
* _After a long press of the Mode button:_
    * Temperature Display - shows the current temperature, if a temperature sensor is available. If not, this watch face is skipped.
    * Battery - Shows the current battery voltage.
    * Settings - Allows you to configure your device. You can set: clock mode (12/24 hour), button volume (no beep / low / high), Timeout (for some watch faces to snap back to the Clock view), low energy timeout (how long until entering sleep mode), LED duration and finally LED color (red / green / blue from 0 to 15).
    * Time Set - Allows you to set the system time. You will first set the year, month and day, then the time zone, then the hour, minute and second.

Second Movement Activity Explorer
---------------------------------

**Required Sensor Board:** Motion Sensor

* Sensor Watch Pro
    1. [Original Casio display](/docs/firmware/download/activity_pro_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/activity_pro_custom.uf2)
* Sensor Watch Classic (green boards)
    1. [Original Casio display](/docs/firmware/download/activity_green_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/activity_green_custom.uf2)
* Limited Edition Sensor Watch (blue boards)
    1. [Original Casio display](/docs/firmware/download/activity_blue_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/activity_blue_custom.uf2)

_Does not work with Sensor Watch Lite, which lacks exposed I2C pins._

This firmware image contains the following watch faces: 

* Simple Clock - A basic clock with date for timekeeping. Long press ALARM to toggle hourly chime.
* World Clock - Long press ALARM to configure with a custom two- or three-letter title and time zone.
* Sunrise/Sunset - Local sunrise and sunset times. (Press Alarm to see the next sunrise / sunset)
* Moon Phase - Today's moon phase. (press Alarm to see days in the future, if you want to know i.e. the next full moon)
* Stopwatch (by Wesley Ellis) - A stopwatch with one-second resolution.
* Countdown (by Wesley Ellis) - A countdown timer.
* Alarm (by Josh Berson) - A simple alarm that fires daily at the same time.
* _After a long press of the Mode button:_
    * Activity Log - A 14-day log of active minutes, defined as two consecutive minutes with acceleration over a given threshold.
    * Temperature Display - shows the current temperature. On Pro, this will use the on-board thermistor; on green and blue boards, it will use the accelerometer's temperature sensor.
    * Battery - Shows the current battery voltage.
    * Accelerometer Status - Shows whether the accelerometer believes the wearer is "Still" or "Active". This state latches for about 10 seconds. A long press of ALARM allows you to change the threshold for "Active" detection.
    * Settings - Allows you to configure your device. You can set: clock mode (12/24 hour), button volume (no beep / low / high), Timeout (for some watch faces to snap back to the Clock view), low energy timeout (how long until entering sleep mode), LED duration and finally LED color (red / green / blue from 0 to 15).
    * Time Set - Allows you to set the system time. You will first set the year, month and day, then the time zone, then the hour, minute and second.
