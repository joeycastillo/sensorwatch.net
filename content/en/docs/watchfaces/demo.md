---
title: "Demo Faces"
linkTitle: "Demo Faces"
weight: 8
---
 * [Character Set](#character-set)
 * [Chirpy](#chirpy)
 * [Demo](#demo)
 * [Frequency Correction](#frequency-correction)
 * [Hello There](#hello-there)
 * [LIS2DW](#demo)
 * [Demo](#demo)

These watch faces demonstrate functionality of the watch, and aren't generally watch faces you'd build into a working firmware.

Character Set
-------------
[`character_set_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/character_set_face.h)

This watch face displays all of the characters in the Sensor Watch character set. You can advance from one character to the next with a short press of the Alarm button.

This watch face may be useful to watch face developers, in that it can help them to understand which characters will work in different positions.

Chirpy
------
[`chirpy_demo_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/chirpy_demo_face.h)

This face demonstrates the chirpy-tx library. It is intended to help you
include chirpy-tx in your own watch faces that need to transmit data out
of the watch.

The face's first screen lets you select from a few built-in transmissions:

SCALE cycles through frequencies in fixed increments. This is intended to
collect and analyze audio samples from different watches. With this info
it may be possible to improve chirpy-tx's parameters like the frequencies
it uses to make the method more robust.

SHORT is a small transmission that contains data taked from the activity_face.

LONG is a longer transmission that contains the first two strophes of a
famous sea shanty.

Select the transmission you want with ALARM, the press LONG ALARM to chirp.

To record and decode a chirpy transmission on your computer, you can
[use the web app here](https://jealousmarkup.xyz/off/chirpy/rx/).

Demo
----
[`demo_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/character_set_face.h)

This watch was designed for the Crowd Supply marketing team, so they could photograph the various functions of Sensor Watch. The Alarm button advances through static screens that simulate different watch faces.

This watch face may only be useful to you if you need to photograph Sensor Watch, i.e. for a blog post.

Frequency Correction
--------------------
[`frequency_correction_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/frequency_correction_face.h)

While active, this face generates a square-wave on pin A1 of the 9-pin
connector. The output frequency is adjustable from 64 Hz to 0.5 Hz.
Long-press ALARM to cycle through available frequencies.

This face also displays the value of the watch's frequency-correction
register. This setting varies from -127 to +127. Press LIGHT to increment
or ALARM to decrement the setting.

Hello There
-----------
[`hello_there_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/hello_there_face.h)

A simple demo that displays the word "Hello" and then the word "there",
on an endless loop. Press ALARM to pause or resume the animation.

LIS2DW Accelerometer Data Logger
--------------------------------
[`lis2dw_logging_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/lis2dw_logging_face.h)

This is an experimental watch face for logging data on the “Sensor Watch Motion Express” board. I will add more documentation for this watch face once this sensor board is more widely available.

Voltage
-------
[`voltage_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/voltage_face.h)

This watch face is very simple and has no controls to speak of. It displays the battery voltage as measured by the SAM L22's ADC.

Note that the Simple Clock watch face includes a low battery warning, so you don't technically need to this watch face unless you want to track the battery level.
