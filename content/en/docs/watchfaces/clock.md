---
title: "Clocks"
linkTitle: "Clocks"
weight: 8
---
The core function of a watch is telling time. All of the watch faces in this category tell time in one form or another.

* [Simple Clock](#simple-clock)
* [World Clock](#world-clock)
* [Beat Time](#beat-time)
* [Mars Time](#mars-time)

Simple Clock
------------

The Simple Clock watch face echoes the classic time and date display of the stock F-91W. It displays the day of the week and day of the month on the top line, along with the current time on the bottom line. Pressing the Light button illuminates the LED so that you can read the display in the dark. Holding the Light button keeps the LED on while the button is held.

If you soldered the buzzer connector to your Sensor Watch board, you may also toggle the Hourly Chime feature by pressing and holding the Alarm button. When you release the Alarm button, the Signal indicator will turn on, indicating that the hourly chime is enabled.

The Simple Clock face also incorporates a low battery warning: this watch face will display the LAP indicator when it detects that the battery voltage is low. This does not mean that power failure is imminent, but it does mean that your battery has only about 5% of its original capacity remaining and you should start thinking about a replacement. The battery is a CR2016 coin cell.

World Clock
-----------

The World Clock watch face looks similar to the Simple Clock watch face, but you'll notice that at first launch the day of week indicators are blank. That's because this watch face does not display the day of the week. Instead, you may customize these letters to display the name of a time zone of your choosing.

To customize this watch face, press and hold the Alarm button. The first letter in the top row will begin flashing. Press the Alarm button repeatedly to advance through the available letters in the first slot, then press the Light button to move to the second letter. Finally, press Light again to move to the time zone setting, and press Alarm to cycle through the available time zones. Press Light one last time to return to the world clock display.

Note that the second slot cannot display all letters or numbers. Also note that at this time, time zones do not automatically update for daylight saving time; you will need to manually adjust this field each spring and fall.

Beat Time
---------

The Beat Time face displays the current Swatch Internet Time, or .beat time. This is a decimal time system that divides the day into 1000 beats.

The three large digits in the bottom row indicate the current beat, and the two smaller digits (normally the seconds in Simple Clock) indicate the fractional beat; so for example you can read “672<small>14</small>” as “beat 672.14”.

Mars Time
---------

This watch face is dedicated to Martian timekeeping. It has several modes, and can display either a time or a date. Pressing the Alarm button cycles through different time zones on Mars:

* MC - Mars Coordinated Time, the time at Airy-0 Crater on the Martian prime meridian
* ZH - Local mean solar time for the Zhurong rover
* PE - LMST for the Perseverance rover
* IN - LMST for the Insight lander
* CU - LMST for the Curiousity rover

Press the Light button to toggle between displaying time and date:

* MC S - the Mars Sol Date, Martian days since December 29, 1873
* ZH Sol - Mission sol for the Zhurong rover
* PE Sol - Mission sol for the Perseverance rover
* IN S - Mission sol for the InSight lander
* CU S - Mission sol for the Curiousity rover

Note that where the mission sol is below 1000, this watch face displays the word “Sol” on the bottom line. When the mission sol is over 1000, the word “Sol” will not fit and so it displays a stylized letter S at the top right.
