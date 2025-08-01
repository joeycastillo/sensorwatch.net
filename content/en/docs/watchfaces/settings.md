---
title: "Settings"
linkTitle: "Settings"
weight: 8
---
The watch faces in this section relate to watch configuration.

 * [Finetune](#finetune)
 * [Nanosec](#nanosec)
 * [Place](#place)
 * [Preferences](#preferences)
 * [Time Set](#time-set)
 * [Time Set Hackwatch](#time-set-hackwatch)

Finetune
--------
[`finetune_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/finetune_face.h)

FineTune face allows to align watch with sub-second precision in 25/250ms
accuracy. Counts time since previous finetune, and allows to calculate &
apply ppm correction for nanosec.

Best used in conjunction with the NANOSEC face.

For more information, refer to [Calibration with Nanosec](../nanosec/).

Nanosec
-------
[`nanosec_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/nanosec_face.h)

The goal of nanosec face is dramatic improvement of SensorWatch accuracy.
Minimum goal is <60 seconds of error per year. Full success is if we can
reach <15 seconds per year (<0.47ppm error).

Best used in conjunction with the FINETUNE face.

For more information, refer to [Calibration with Nanosec](../nanosec/).

Place
-----
[`place_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/place_face.h)

Based on and expanded from the Sunrise/Sunset face. Outsourced the location setting functionality to 
its own face. Also serves as a converter between different coordinate notation formats.

With the LIGHT button each place coordinate can be shown and edited in 4 different display modes:

1) Decimal Latitude and Longitude (WGS84) up to 5 decimal points
2) Latitude and Longitude (WGS84) in traditional DD°MM'SS" notation
3) Ten digit Open Location Code (aka. PlusCode) format
4) Ten digit Geohash format

Using the ALARM button the user can flip through 2 pages of coordinate info to see the first and
second sets of digits.

(please also refer to the notes on precision below)

#### Editing Mode

A LONG PRESS of the LIGHT button toggles editing mode for each of the selected notations.

In this mode LIGHT moves the cursor and ALARM changes the letter cycling through the available
alphabet or numbers. 

When OLC or Geohash display are edited, Digit Info mode is activated. It serves as a workaround 
for the limitation of how ambiguously alphanumeric characters are displayed on the main seven segment 
digits of the watch face ( S or 5, I or 1, U or W?).

The selected letter is also shown in the much easier to read alphanumeric 8 segment weekday digit above.
In addition the '24H' indicator is active when the selected digit represents a number and the 'PM' 
indicator for a letter. 

A LONG PRESS of LIGHT saves the changes.

Coordinates are read or stored to both the traditional internal location register and a file on 
the LFS file system ("place.loc"). By default the Watch Face loads the coordinates from file
when activated. If no file is present, the coordinates are loaded from the register.
(please also see the notes on precision below)

#### Auxiliary Mode: Digit Info

A LONG PRESS of the ALARM button toggles Digit Info mode when OLC or Geohash display is active.
(LAP indicator is on) It is a means of being able to see the detailed Digit Info as described above
but without the risk of accidentally editing any of digits.

Both ALARM and LIGHT buttons can be used to flip through the letters.

#### Notes on Coordinate Precision

The common WGS84 Latitude and Longitude degrees naturally do not represent meters in distance 
on the ground. 1° Longitude on the equatorial line equals a width of 111.32 kilometers, but 
at 40° latitude further North or South it is approximately 85 kilometers wide. The closer to 
the poles the narrower (and more precise) the latitude degrees get.

The Sensor Watch's traditional 16bit location register only stores latitudes and longitudes 
with two decimal points. That equals a longitudal precision of 36 arc seconds, or ~1111 meters
at the equator - precise enough for astronomical calculations, but not if you want to store the 
location of let's say a building.

Hence we propose the <place.loc> file that serves the same purpose, but with a precision of 
five decimal digits. That equals 0.04 arc seconds or 1.11 meters at the equator.

Please also note that the different notations of this watch face also have varying magnitudes 
of precision:

| Format             | Notation               | Precision at Equator | Precision at 67° N/S |
| ------------------ | ---------------------- | -------------------- | -------------------- |
| 2d. Decimal LatLon | 29.98, 31.13           |           1111.320 m |            435.125 m |
| 5d. Decimal LatLon | 29.97916, 31.13417     |              1.111 m |              0.435 m |
| DMS LatLon         | N 29°58′45″, E 31°8′3″ |             30.833 m |             12.083 m |
| Open Location Code | 7GXHX4HM+MM            |             13.875 m |             13.875 m |
| Geohash            | stq4s3x1qu             |              1.189 m |              0.596 m |

Since all notations are internally converted into degrees with 5 decimal points, expect some
rounding errors when editing or loading the coordinates in other notation formats.

Preferences
-----------
[`preferences_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/preferences_face.h)

The Preferences watch face allows you to configure various options on your Sensor Watch. Like all other screens, you advance the field you’re setting with the Light button, and advance its value with the Alarm button. The Preferences watch face labels each setting with a two-letter code on the top row; the following list describes each setting and their options:

CL - Clock mode. This setting allows you to select a 12-or 24-hour clock display. All watch faces that support displaying the time will respect this setting; for example, both Simple Clock, World Clock and Sunrise/Sunset will display the time in 24 hour format if the 24 hour clock is selected here.

BT - Button tone. This setting is only relevant if you installed the buzzer connector, and it toggles the beep when changing modes. If Y, the buzzer will sound a tone when Mode is pressed. Change to N to make the Mode button silent.

TO - Timeout. Sets the time until screens that time out (like Settings and Time Set) snap back to the first screen. 60 seconds is a good default for the stock firmware, but if you choose a custom firmware with faces that you’d like to keep on screen for longer, you can set that here.

LE - Low Energy mode. Sets the time until the watch enters its low energy sleep mode. Options range from 1 hour to 7 days, or Never. The more often Sensor Watch goes to sleep, the longer its battery will last — but you will lose the seconds indicator while it is asleep. This setting allows you to make a tradeoff between the device’s responsiveness and its longevity.

LT - Light. This setting has three screens:

* The first lets you choose how long the LED should stay lit when the Light button is pressed. Options are 1 second, 3 seconds and 5 seconds, or “No LED” to disable the LED entirely.
* The second screen, titled “blu”, sets the intensity of the blue LED. Values range from 0 (off) to 15 (full intensity)
* The third screen, “red”, sets the intensity of the red LED, again from 0 to 15.
On the last two screens, the LED remains on so that you can see the effect of mixing the two LED colors. On the Special Edition boards, you’ll have red, blue and a variety of shades of pink and purple to experiment with!

Time Set
--------
[`set_time_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/set_time_face.h)

The Time Set watch face allows you to set the time on Sensor Watch. Use the Light button to advance through the field you are setting, and the Alarm button to change the value in that field. The fields are, in order: Hour, Minute, Second, Year, Month, Day and Time Zone.

For features like World Clock and Sunrise/Sunset to work correctly, you must set the time to your local time, and the time zone to your local time zone. This allows Sensor Watch to correctly offset the time. This also means that when daylight savings time starts or ends, you must update both the time and the time zone on this screen.

Time Set Hackwatch
------------------
[`set_time_hackwatch_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/settings/set_time_hackwatch_face.h)

This is an extended version of set_time face which allow setting seconds
precisely. To achieve that - press and hold alarm button few seconds before
00 and release exaclty as reference clock turns 00.

All settings can go up, or down (long alarm press).

The challenge is that SensorWatch display is delayed 0.5 seconds vs hardware
RTC clock. It is caused by interrupts being generated by raising edge of
counter. It means there is no way to precisely trigger at 0.5s, as events
at different frequencies slightly mismatch. This watch face achieves this
approximately by triggering at 15th out of 32Hz events.

If you are <30 seconds when setting seconds - you will stay in the same
minute. Otherwise - you will go to next minute.

Note that changing anything will slightly delay subseconds counter. This
is why this face sets seconds last to achieve best precision. Still,
best possible precision is achieved with finetune face.
