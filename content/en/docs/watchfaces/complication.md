---
title: "Complications"
linkTitle: "Complications"
weight: 8
---
In horology, a complication is an additional set of gears in a mechanical watch movenent that enables a secondary function, such as a sunrise/sunset dial. The watch faces in this category do just that.

 * [Sunrise/Sunset](#sunrisesunset)
 * [Moon Phase](#moon-phase)
 * [Stopwatch](#stopwatch)
 * [Countdown](#countdown)
 * [Counter](#counter)
 * [Pulsometer](#pulsometer)
 * [Tomato Productivity Timer](#tomato-productivity-timer)
 * [TOTP Generator](#totp-generator)
 * [Day One](#day-one)
 * [Blinky Light](#blinky-light)
 * [Astronomy](#astronomy)
 * [Orrery](#orrery)

Sunrise/Sunset
--------------

This watch face displays local sunrise and sunset times. During the day, it displays today's sunset; at night, it displays tomorrow's sunrise.

When you first see this watch face, it will display “No Loc”, or No Location. This is because your latitude and longitude are required to calculate sunrise and sunset. When on this screen, you can set your location in a similar way to the World Clock screen.

Press and hold Alarm to enter location setting mode. The top line will read “LA” (Latitude), and the bottom line “+ 0000”. The large digits are the whole number part of the latitude, and the smaller digits (in the seconds place) are the fractional part. Enter your latitude and longitude (“LO”) by pressing the Alarm button to change the sign or advance the digits, and the Light button to move to the next character; for example, a latitude of 40.73° N would be “+ 40<small>73</small>”, and a longitude of 73.94° W would be “–073<small>94</small>”.

Once you have set your latitude and longitude, the Sunrise/Sunset face will display the next sunrise or sunset on the bottom row, and the day of that sunrise or sunset at the top right.

A short press on the Alarm button will advance to the following sunrise or sunset: for example, on Monday afternoon, it will display Monday evening’s sunset, but a short press on the Alarm button will display Tuesday morning’s sunrise.

If you made a mistake while entering your location, or if you simply wish to change your location, you can re-enter location setting mode with another long press on the Alarm button.

Moon Phase
----------

The Moon Phase face is similar to the Sunrise/Sunset face: it displays the current phase of the moon, along with the day of the month and a graphical representation of the moon on the top row.

This graphical representation is a bit abstract. The segments that turn on represent the shape of the moon, waxing from the bottom right and waning at the top left. A small crescent at the bottom right will grow into a larger crescent, then add lines in the center for a quarter and half moon. All segments are on during a full moon. Then gradually the segments at the bottom right will turn off, until all that remains is a small waning crescent at the top left.

All segments turn off during a new moon.

On this screen you may press the Alarm button repeatedly to move forward in time: the day of the month at the top right will advance by one day for each button press, and both the text and the graphical representation will display the moon phase for that day. Try pressing the Alarm button 27 times now, just to visualize what the moon will look like over the next month.

Stopwatch
---------

TODO

Countdown
---------

TODO

Counter
-------

TODO

Pulsometer
----------

The Pulsometer is an implementation of a sort of a classic mechanical watch complication. A [classic pulsometer complication](https://watchtime.me/news/features/article/1424/what-is-a-pulsometer-scale-7-cool-doctor-s-watches) involves a chronograph with a scale calibrated for counting a certain number of heartbeats (often 30). You start it and begin counting heartbeats, and stop it after counting the specified number of beats. Once stopped, the needle will point to your heart rate.

The pulsometer on Sensor Watch flashes its instructions at launch: “Hold Alarm + count 30 beats.” Using the hand on the side where you wear your watch, touch your carotid artery (in your neck) and feel for your pulse. Once you find it, use your other hand to press and hold the Alarm button, and count your heartbeats. When you reach 30 beats, release the Alarm button. The display will show a number such as “60 bpm”; this is your heart rate in beats per minute.

Two notes: 

1. For the first few seconds of a measurement, the display will read “Hi”. This indicates that it's too early for the measured value to be a valid heart rate. Once the measurement is below 240 bpm, the display will update.
2. If you hold the button down for more than 45 seconds, the display will read “Lo”. If it took this long for you to count 30 heartbeats, this indicates that your heart rate is below 40 beats per minute.

Tomato Productivity Timer
-------------------------

TODO

TOTP Generator
--------------

TODO

Day One
-------

This watch face displays the number of days since a given date. It was originally designed to display the number of days you've been alive, but technically it can count up from any date in the 20th century or the 21st century, so far.

Long press on the Alarm button to enter customization mode. The text "YR" will appear, and will allow you to set the year starting from 1959. Press Alarm repeatedly to advance the year. If your birthday is before 1959, advance beyond the current year and it will wrap around to 1900. Once you have set the year, press Light to set the month ("MO") and day ("DA"), advancing the value by pressing Alarm repeatedly.

Note that at this time, the Day One face does not display the sleep indicator in sleep mode, which may make the watch appear to be unresponsive in sleep mode. You can still press the Alarm button to wake the watch. This UI quirk will be addressed in a future update.

Blinky Light
------------

The blinky light watch face was designed as a tutorial for making a watch face in Movement, but it actually might be useful to have a blinking light in a pinch.

The screen displays the name of the watch face (”BL”), as well as an S at the top right for slow blink or an F for fast blink. The bottom line selects the color: green, red or yellow. You can change the speed of the blinking light by pressing the Alarm button, and change the color with the Light button. A long press on the Alarm button starts the blinking light, and another long press stops it.

**Note that this will chew through your battery!** The green LED uses about 450µA at full brightness, which is 45 times the normal power consumption of the watch. The red LED is an order of magnitude less efficient (4500 µA), and the yellow setting lights both LEDs, which chews through nearly 5 milliamperes. This means that one hour of yellow blinking is likely to eat up between 2 and 3 percent of the battery's usable life! Still, if you need to signal your location to someone in a dark forest, this watch face could come in handy.

Just try to use the green LED as much as you can.

Astronomy
---------

The Astronomy watch face is among the most complex watch faces in the Movement collection. It allows you to calculate the locations of celestial bodies in the sky, as well as distance in astronomical units (or, in the case of the Moon, distance in kilometers).

When you arrive at the Astronomy watch face, you'll see its name (“Astro”) and an animation of two objects orbiting each other. You will also see "SO" (for Sol) flashing in the top left. The flashing letters indicate the currently selected celestial body. Short press Alarm to advance through the available celestial bodies:

* SO - Sol, the sun
* ME - Mercury
* VE - Venus
* LU - Luna, the Earth's moon
* MA - Mars
* JU - Jupiter
* SA - Saturn
* UR - Uranus
* NE - Neptune

Once you've selected the celestial body whose parameters you wish to calculate, long press the Alarm button and relase it. The letter “C” will flash while the calculation is performed.

When the calculation is complete, the screen will display the altitude (“aL”) of the celestial body. You can cycle through the available parameters with repeated short presses on the Alarm button:

* aL - Altitude (in degrees), the elevation over the horizon. If negative, it is below the horizon.
* aZ - Azimuth (in degrees), the cardinal direction relative to true north.
* rA - Right Ascension (in hours/minutes/seconds)
* dE - Declination (in degrees/minutes/seconds)
* di - Distance (the digits in the top right will display either aU for astronomical units, or K for kilometers)

Long press on the Alarm button to select another celestial body.

Orrery
------

The Orrery watch face is similar to the Astronomy watch face in that it calculates properties of the planets, but instead of calculating their positions in the sky, this watch face calculates their absolute locations in the solar system. This is only useful if you want to plot the planets on graph paper, but hey, you never know!

The controls are identical to the Astronomy watch face: while the title screen (“Orrery”) is displayed, you can advance through the available planets with repeated short presses on the Alarm button. The available planets:

* ME - Mercury
* VE - Venus
* EA - Earth
* LU - Luna, the Earth's moon
* MA - Mars
* JU - Jupiter
* SA - Saturn
* UR - Uranus
* NE - Neptune

Note that the sun is not available in this menu, as the sun is always at (0,0,0) in this calculation.

Long press on the Alarm button to calculate the planet's location, and after a flashing “C” (for Calculating), you will be presented with the planet's X coordinate in astronomical units. Short press Alarm to cycle through the X, Y and Z coordinates, and then long press Alarm to return to planet selection.

The large numbers represent the whole number part, and the two smaller numbers (in the seconds place) represent the decimal portion. So if you see “SA X 7<small>36</small>” and “SA Y -6<small>62</small>”, you can read that as an X coordinate of 7.36 AU and a Y coordinate of -6.62 AU. You can literally draw a dot at (0, 0) to represent the sun, and a dot at (7.36, -6.62) to represent Saturn. (the Z coordinates tend to be pretty close to zero, as the planets largely orbit on a single plane, the ecliptic)
