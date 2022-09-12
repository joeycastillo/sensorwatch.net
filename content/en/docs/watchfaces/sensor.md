---
title: "Sensors"
linkTitle: "Sensors"
weight: 8
---
Sensor Watch is designed to display data from sensors. The watch faces in this category read sensor data and present it in a useful way.

* [Voltage](#voltage)
* [Temperature Display](#temperature-display)
* [Temperature Log](#temperature-log)
* [Temperature Testing](#temperature-testing)
* [LIS2DW Accelerometer Data Logger](#lis2dw-accelerometer-data-logger)

Voltage
-------

This watch face is very simple and has no controls to speak of. It displays the battery voltage as measured by the SAM L22's ADC.

Note that the Simple Clock watch face includes a low battery warning, so you don't technically need to this watch face unless you want to track the battery level.

Temperature Display
-------------------

This watch face is designed to work with either the Temperature + GPIO sensor board or the Temperature + Light sensor board. It reads the current temperature from the thermistor voltage divider on the sensor board, and displays the current temperature in degrees Celsius.

When the watch is on your wrist, your body heat interferes with an ambient temperature reading, but if you set it on a bedside table, strap it to your bike handlebars or place it outside of your tent while camping, this watch face can act as a digital thermometer for displaying ambient conditions.

The temperature sensor watch face automatically samples the temperature once every five seconds, and it illuminates the Signal indicator just before taking a reading.

Pressing the Alarm button toggles the unit display from Celsius to Fahrenheit. Technically this sets the global “Metric / Imperial” flag, so any other watch face that displays localizable units will display them in the system selected here.

Temperature Log
---------------

This watch face automatically logs the temperature once an hour, and maintains a 36-hour log of readings. This watch face is admittedly rather complex, and bears some explanation.

The main display shows the letters “TL” in the top left, indicating the name of the watch face. At the top right, it displays the index of the reading; 0 represents the most recent reading taken, 1 represents one hour earlier, etc. The bottom line in this mode displays the logged temperature.

A short press of the “Alarm” button advances to the next oldest reading; you will see the number at the top right advance from 0 to 1 to 2, all the way to 35, the oldest reading available.

A short press of the “Light” button will briefly display the timestamp of the reading. The letters at the top left will display the word "At", and the main line will display the timestamp of the currently displayed data point. The number in the top right will display the day of the month for the given data point; for example, you can read “At 22 3:00 PM” as ”At 3:00 PM on the 22nd”.

If you need to illuminate the LED to read the data point, long press the Light button and release it.

Temperature Testing
-------------------

This watch face is similar to the Temperature watch face, but it updates the temperature several times per second. You likely don't need this watch face, but it is useful for testing the temperature sensor boards.

LIS2DW Accelerometer Data Logger
--------------------------------

This is an experimental watch face for logging data on the “Sensor Watch Motion Express” board. I will add more documentation for this watch face once this sensor board is more widely available.
