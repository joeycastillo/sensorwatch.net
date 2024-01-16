---
title: "Sensors"
linkTitle: "Sensors"
weight: 8
---
Sensor Watch is designed to display data from sensors. The watch faces in this category read sensor data and present it in a useful way.

* [Accelerometer Data Acquisition](#accelerometer-data-acquisition)
* [Light Meter](#light-meter)
* [Temperature Display](#temperature-display)
* [Temperature Log](#temperature-log)
* [Temperature Testing](#temperature-testing)

Accelerometer Data Acquisition
------------------------------
[`accelerometer_data_acquisition_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/sensor/accelerometer_data_acquisition_face.h)

TODO: Add description here, including controls.

Light Meter
-----------
[`lightmeter_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/sensor/lightmeter_face.h)

Aperture-priority Light Meter Face

Tested with the "Q3Q-SWAB-A1-00 Temperature + Test Points + OPT3001" flexboard.
This flexboard could use a revision: 

 - The thermistor components should be moved west a mm or flipped to the backside
   to avoid stressing the flexboard against the processor so much.
 - The 'no connect' pad falls off easily.

Controls:

 - Trigger a measurement by long-pressing Alarm.
   Sensor integration is happening when the Signal indicator is on.

 - ISO setting can be cycled by long-pressing Light.
   During integration the current ISO setting will be displayed. 

 - EV measurement in the top right: "LAP" indicates "half stop". 
   So "LAP -1" means EV = -1.5. Likewise "LAP 13" means EV = +13.5  

 - Aperture in the bottom right: the last 3 main digits are the f-stop. 
   Adjust this number in half-stop increments using Alarm = +1/2 and Light = -1/2. 

 - Best shutter speed in the bottom left: the first 3 digits are the shutter speed. 
   Some special chars are needed here: "-" = seconds, "h" = extra half second, "K" = thousands.
   "HI" or "LO" if there's no shutter in the dictionary within 0.5 stops of correct exposure.

 - Mode long-press changes the main digits to show raw sensor lux measurements.

Temperature Display
-------------------
[`thermistor_readout_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/sensor/thermistor_readout_face.h)

This watch face is designed to work with either the Temperature + GPIO sensor board or the Temperature + Light sensor board. It reads the current temperature from the thermistor voltage divider on the sensor board, and displays the current temperature in degrees Celsius.

When the watch is on your wrist, your body heat interferes with an ambient temperature reading, but if you set it on a bedside table, strap it to your bike handlebars or place it outside of your tent while camping, this watch face can act as a digital thermometer for displaying ambient conditions.

The temperature sensor watch face automatically samples the temperature once every five seconds, and it illuminates the Signal indicator just before taking a reading.

Pressing the Alarm button toggles the unit display from Celsius to Fahrenheit. Technically this sets the global “Metric / Imperial” flag, so any other watch face that displays localizable units will display them in the system selected here.

Temperature Log
---------------
[`thermistor_logging_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/sensor/thermistor_logging_face.h)

This watch face automatically logs the temperature once an hour, and maintains a 36-hour log of readings. This watch face is admittedly rather complex, and bears some explanation.

The main display shows the letters “TL” in the top left, indicating the name of the watch face. At the top right, it displays the index of the reading; 0 represents the most recent reading taken, 1 represents one hour earlier, etc. The bottom line in this mode displays the logged temperature.

A short press of the “Alarm” button advances to the next oldest reading; you will see the number at the top right advance from 0 to 1 to 2, all the way to 35, the oldest reading available.

A short press of the “Light” button will briefly display the timestamp of the reading. The letters at the top left will display the word "At", and the main line will display the timestamp of the currently displayed data point. The number in the top right will display the day of the month for the given data point; for example, you can read “At 22 3:00 PM” as ”At 3:00 PM on the 22nd”.

If you need to illuminate the LED to read the data point, long press the Light button and release it.

Temperature Testing
-------------------
[`thermistor_testing_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/sensor/thermistor_testing_face.h)

This watch face is similar to the Temperature watch face, but it updates the temperature several times per second. You likely don't need this watch face, but it is useful for testing the temperature sensor boards.
