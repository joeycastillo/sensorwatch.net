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

TODO

Demo
----
[`demo_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/character_set_face.h)

This watch was designed for the Crowd Supply marketing team, so they could photograph the various functions of Sensor Watch. The Alarm button advances through static screens that simulate different watch faces.

This watch face may only be useful to you if you need to photograph Sensor Watch, i.e. for a blog post.

Frequency Correction
--------------------
[`frequency_correction_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/frequency_correction_face.h)

TODO

Hello There
-----------
[`hello_there_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/hello_there_face.h)

TODO

LIS2DW Accelerometer Data Logger
--------------------------------
[`lis2dw_logging_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/lis2dw_logging_face.h)

This is an experimental watch face for logging data on the “Sensor Watch Motion Express” board. I will add more documentation for this watch face once this sensor board is more widely available.

Voltage
-------
[`voltage_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/demo/voltage_face.h)

This watch face is very simple and has no controls to speak of. It displays the battery voltage as measured by the SAM L22's ADC.

Note that the Simple Clock watch face includes a low battery warning, so you don't technically need to this watch face unless you want to track the battery level.
