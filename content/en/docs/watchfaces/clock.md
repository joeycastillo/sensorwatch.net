---
title: "Clocks"
linkTitle: "Clocks"
weight: 8
---
The core function of a watch is telling time. All of the watch faces in this category tell time in one form or another.

* [Beat Time](#beat-time)
* [Binary LED Clock](#binary-led-clock)
* [Decimal Time](#decimal-time)
* [Mars Time](#mars-time)
* [Repetition Minute](#repetition-minute)
* [Simple Clock](#simple-clock)
* [Week Number Clock](#week-number-clock)
* [World Clock](#world-clock)
* [World Clock 2](#world-clock-2)
* [Wyoscan](#wyoscan)

Beat Time
---------
[`beats_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/beats_face.h)

The Beat Time face displays the current Swatch Internet Time, or .beat time. This is a decimal time system that divides the day into 1000 beats.

The three large digits in the bottom row indicate the current beat, and the two smaller digits (normally the seconds in Simple Clock) indicate the fractional beat; so for example you can read “672<small>14</small>” as “beat 672.14”.

Binary LED Clock
----------------
[`simple_clock_bin_led_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/simple_clock_bin_led_face.h)

A "fork" of the simple clock face, which provides the functionality of showing 
the current time by flashing the LED using binary representation.

This feature serves as a practical solution to compensate for the admittedly 
subpar backlight of the F91w watch and is especially useful if your eyesight
is not the best. By pressing and holding the light button long enough, the
watch will illuminate the LED to showcase the current time.

How to interpret the flashing led:
- Firstly, the hour is presented as a binary number, with the lowest bit displayed
  first. A short flash signifies 0, while a longer flash represents 1. If you use
  the watch in 24h mode, please note that the indicated value may be decreased 
  by 12, to keep things simple and short. For example, 22h would be translated
  to 10h.
- After showing the hour, a lengthier  pause indicates that minutes will be shown 
  next.
- Similar to the hour representation, minutes are displayed in binary format, 
  starting with the lowest bits. A short flash denotes 0, a longer flash 
  represents 1.

Decimal Time
------------
[`decimal_time_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/decimal_time_face.h)

This face presents the current time as hours and hundredths of an hour. Every hundreth of an hour, or "centihour", 
occurs every 36 seconds. Because they range from 0 to 99, centihours, in the seventies range, will be displayed with a lowercase 7.

See https://en.wikipedia.org/wiki/Decimal_time#Decimal_hours
 
This method of timekeeping is used by the United States Postal Service.
* http://www.branch38nalc.com/sitebuildercontent/sitebuilderfiles/CONVERSION_TABLE_TIME.pdf
* https://postalemployeenetwork.com/time-conversion-print.htm

This method may be used by other organizations as well
* https://www.labor.nc.gov/workplace-rights/employer-responsibilities/time-conversion-chart-minutes-decimal-hours
* https://uh.edu/office-of-finance/payroll/time_conversion_chart_minutes_to_decimalhours.pdf
* https://www.placer.ca.gov/DocumentCenter/View/3860/Decimals-to-Minutes-Conversion-Table-PDF
* https://hr.colostate.edu/minute-to-decimal-conversion-chart/

Many thanks go to Joey Castillo for making this project happen.

Mars Time
---------
[`mars_time_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/mars_time_face.h)

This watch face is dedicated to Martian timekeeping. It has several modes, and can display either a time or a date. Pressing the Alarm button cycles through different time zones on Mars:

* MC - Mars Coordinated Time, the time at Airy-0 Crater on the Martian prime meridian
* ZH - Local mean solar time for the Zhurong rover
* PE - LMST for the Perseverance rover
* IN - LMST for the Insight lander
* CU - LMST for the Curiosity rover

Press the Light button to toggle between displaying time and date:

* MC S - the Mars Sol Date, Martian days since December 29, 1873
* ZH Sol - Mission sol for the Zhurong rover
* PE Sol - Mission sol for the Perseverance rover
* IN S - Mission sol for the InSight lander
* CU S - Mission sol for the Curiosity rover

Note that where the mission sol is below 1000, this watch face displays the word “Sol” on the bottom line. When the mission sol is over 1000, the word “Sol” will not fit and so it displays a stylized letter S at the top right.

Repetition Minute
-----------------
[`repetition_minute_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/repetition_minute_face.h)

A hopefully useful complication for friendly neighbors in the dark

Originating from 1676 from reverend and mechanician Edward Barlow, and
perfected in 1820 by neighbor Abraham Breguet, a minute repeater or 
"repetition minute" is a complication in a mechanical watch or clock that
chimes the hours and often minutes at the press of a button. There are many
types of repeater, from the simple repeater which merely strikes the number
of hours, to the minute repeater which chimes the time down to the minute,
using separate tones for hours, quarter hours, and minutes. They originated
before widespread artificial illumination, to allow the time to be determined
in the dark, and were also used by the visually impaired. 

How to use it :

Long press the light button to get an auditive reading of the time like so :
0..23 (1..12 if 24-hours format isn't enabled) low beep(s) for the hours
0..3 low-high couple pitched beeps for the quarters
0..14 high pitched beep(s) for the remaining minutes

Prerequisite : a watch with a working buzzer

~ Only in the darkness can you see the stars. - Martin Luther King ~

Simple Clock
------------
[`simple_clock_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/simple_clock_face.h)

The Simple Clock watch face echoes the classic time and date display of the stock F-91W. It displays the day of the week and day of the month on the top line, along with the current time on the bottom line. Pressing the Light button illuminates the LED so that you can read the display in the dark. Holding the Light button keeps the LED on while the button is held.

If you soldered the buzzer connector to your Sensor Watch board, you may also toggle the Hourly Chime feature by pressing and holding the Alarm button. When you release the Alarm button, the Signal indicator will turn on, indicating that the hourly chime is enabled.

The Simple Clock face also incorporates a low battery warning: this watch face will display the LAP indicator when it detects that the battery voltage is low. This does not mean that power failure is imminent, but it does mean that your battery has only about 5% of its original capacity remaining and you should start thinking about a replacement. The battery is a CR2016 coin cell.

Week Number Clock
-----------------
[`weeknumber_clock_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/weeknumber_clock_face.h)

Same as simple clock, but has iso 8601 week number instead of seconds counter.

Long-press ALARM to toggle the hourly chime.

World Clock
-----------
[`world_clock_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/world_clock_face.h)

The World Clock watch face looks similar to the Simple Clock watch face, but you'll notice that at first launch the day of week indicators are blank. That's because this watch face does not display the day of the week. Instead, you may customize these letters to display the name of a time zone of your choosing.

To customize this watch face, press and hold the Alarm button. The first letter in the top row will begin flashing. Press the Alarm button repeatedly to advance through the available letters in the first slot, then press the Light button to move to the second letter. Finally, press Light again to move to the time zone setting, and press Alarm to cycle through the available time zones. Press Light one last time to return to the world clock display.

Note that the second slot cannot display all letters or numbers. Also note that at this time, time zones do not automatically update for daylight saving time; you will need to manually adjust this field each spring and fall.

World Clock 2
-------------
[`world_clock2_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/world_clock2_face.h)

This is an alternative world clock face that allows the user to cycle
through a list of selected time zones. It extends the original
implementation by Joey Castillo. The face has two modes: display mode
and settings mode.

Settings mode

When the clock face is activated for the first time, it enters settings
mode. Here, the user can select the time zones they want to display. The
face shows a summary of the current time zone:
 * The top of the face displays the first two letters of the time zone
   abbreviation, such as "PS" for Pacific Standard Time or CE for
   "Central European Time".
 * The upper-right corner shows the index number of the time zone. This
   helps avoid confusion when multiple time zones have the same two-letter
   abbreviation.
 * The main display shows the offset from UTC, with a "+" indicating a
   positive offset and a "-" indicating a negative offset. For example,
   the offset for Japanese Standard Time is displayed as "+9:00".

The user can navigate through the time zones and select them using the
following buttons:
 * The ALARM button moves forward to the next time zone, while the LIGHT
   button moves backward to the previous zone. This way, the user can
   cycle through all 41 supported time zones.
 * A long press on the LIGHT button selects the current time zone, and
   the signal indicator appears at the top left. Another long press of
   the LIGHT button deselects the time zone.
 * A long press on the ALARM button exits settings mode and returns to
   display mode.

Display mode

In the display mode, the face shows the time of the currently selected
time zone. The face includes the following components:
 * The top of the face displays the first two letters of the time zone
   abbreviation, such as "PS" for Pacific Standard Time or "CE" for
   Central European Time.
 * The upper-right corner shows the current day of the month, which helps
   indicate time zones that cross the international date line with respect
   to the local time.
 * The main display shows the time in the selected time zone in either
   12-hour or 24-hour form. There is no timeout, allowing users to keep
   the chosen time zone displayed for as long as they wish.

The user can navigate through the selected time zones using the following
buttons:
 * The ALARM button moves to the next selected time zone, while the LIGHT
   button moves to the previous zone. If no time zone is selected, the
   face simply shows UTC.
 * A long press on the ALARM button enters settings mode and enables the
   user to re-configure the selected time zones.
 * A long press on the LIGHT button activates the LED illumination of the
   watch.

Wyoscan
-------
[`wyoscan_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/clock/wyoscan_face.h)

This is a recreation of the Wyoscan watch, which was a $175 watch in 2014.
It was an f-91w pcb replacement.

Video: https://user-images.githubusercontent.com/1795778/252550124-e07f0ed1-e328-4337-a654-fa1ee65d883f.mp4
Background information: https://artmetropole.com/shop/11460
Demo of what it looks like: https://www.o-r-g.com/apps/wyoscan

8 frames per number * 6 numbers + the trailing 16 frames = 64 frames
at 32 frames per second, this is a 2-second cycle time or 0.5 Hz.

It is giving me a stack overflow after about 2.5 cycles of the time display
in the emulator, but it works fine on the watch.

I'd like to make something for the low energy mode, but I haven't thought
about how that might work, right now it just freezes in low energy mode
until you press the 12-24HR button.

There are no controls; it simply animates as long as the page is active.
