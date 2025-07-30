---
title: "Temperature Display"
linkTitle: "Temperature Display"
weight: 80
---
This watch face reads the current temperature and displays it in degrees Celsius or Fahrenheit. Pressing the Alarm button toggles the unit display from Celsius to Fahrenheit.

Note that ehen the watch is on your wrist, your body heat interferes with an ambient temperature reading, but if you set it on a bedside table, strap it to your bike handlebars or place it outside of your tent while camping, this watch face can act as a digital thermometer for displaying ambient conditions.

The temperature sensor watch face automatically samples the temperature once every five seconds, and it illuminates the Signal indicator just before taking a reading. It automatically uses the most accurate temperature sensor available: if a thermistor is installed (as on Lite, Pro or the classic board with the temperature sensor add-on), it uses that. If you are on a classic board with the accelerometer sensor, it will use the accelerometer's lower-resolution temperature sensor. 

If no temperature sensor is available, this watch face will skip itself by resigning immediately.

Note that the Celsius/Fahrenheit selection on this watch face also sets a global “Metric / Imperial” flag, so any other watch faces that display localizable units will display them in the system selected here.
