---
title: "Prebuilt Alternative Firmware for Sensor Watch"
linkTitle: "Prebuilt Alternative Firmware for Sensor Watch"
weight: 20
---
This section contains the stock firmware for Sensor Watch, as well as several prebuilt firmware images featuring an alternative set of watch faces. To flash one of these firmware images to your Sensor Watch, [follow the instructions here](/docs/firmware/flashing/).

### Prebuilt Firmwares

Note that each firmware comes in two flavors, depending on the color of your circuit board. This is because blue boards have a red/blue LED and green boards have a red/green LED, and the pins are swapped. No damage will result from loading the wrong firmware onto your board, but the LED colors will be wrong. 

Also note that all of these have the "Preferences" and "Time Set" screens at the end; for brevity they aren't included in this listing, but you will always have access to them.

* [Movement Standard Edition](#movement-standard): Simple Clock, World Clock, Sunrise/Sunset, Moon Phase, Stopwatch
* [Movement Backer Edition](#movement-backer-edition-with-temperature-display): Simple Clock, World Clock, Sunrise/Sunset, Moon Phase, Temperature
* [Focus](#focus): Simple Clock, Tomato Timer, Stopwatch, Countdown
* [The Athlete](#the-athlete): Simple Clock, Stopwatch, Countdown, Exercise Counter, Pulsometer
* [The Backpacker](#the-backpacker): Simple Clock, Sunrise/Sunset, Moon Phase, Temperature, Temperature Log, Blinky Light
* [The Stargazer](#the-stargazer): Simple Clock, Astronomy, Sunrise/Sunset, Moon Phase
* [Deep Space Now](#deep-space-now): Simple Clock, Mars Time, World Clock x3
* [alt.time](#alttime): Simple Clock, Beat Time, Day One

Movement Standard
-----------------

This is the standard firmware for Movement. It's packed, but not jam-packed:

* Simple Clock - A basic clock with date for timekeeping.
* World Clock - You can configure this with a custom two-letter title and any time zone.
* Sunrise/Sunset - Local sunrise and sunset times.
* Moon Phase - Tonight's moon phase. (press Alarm to see days in the future)
* Stopwatch (by Wesley Ellis) - A simple stopwatch with one-second resolution.

Download it now: for [Red Boards](/docs/firmware/download/standard-red.uf2), [Green Boards](/docs/firmware/download/standard-green.uf2) and [Blue Boards](/docs/firmware/download/standard-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/standard/)

Movement: Backer Edition (with temperature display)
---------------------------------------------------

**Required Sensor Board:** Temperature Sensor

The first Sensor Watch boards that shipped were with orders that automatically included a temperature sensor board. As such, the set of watch faces that shipped with those boards included a temperature display.

Post-campaign, the temperature sensor board was optional, so we replaced the temperature display with a stopwatch. If you bought a temperature sensor board and wish to have a temperature display, use this firmware; it's identical to the standard firmware, but replaces the stopwatch with a temperature display.

* Simple Clock - A basic clock with date for timekeeping.
* World Clock - You can configure this with a custom two-letter title and any time zone.
* Sunrise/Sunset - Local sunrise and sunset times.
* Moon Phase - Tonight's moon phase. (press Alarm to see days in the future)
* Temperature - As measured from the temperature sensor board. (Alarm toggles C or F)

Download it now: for [Red Boards](/docs/firmware/download/backer-red.uf2), [Green Boards](/docs/firmware/download/backer-green.uf2) and [Blue Boards](/docs/firmware/download/backer-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/backer/)

Focus
-----

**Required Mod:** Tomato and countdown timer requires soldering the buzzer connector.

For folks who want to use the watch for productivity.

* Simple Clock - A basic clock with date for timekeeping.
* Tomato Timer (by Wesley Ellis) - A productivity timer varietal.
* Stopwatch (by Wesley Ellis) - A simple stopwatch with one-second resolution.
* Countdown (by Wesley Ellis) - A simple countdown timer for eggs, tea or tasks.

Download it now: for [Red Boards](/docs/firmware/download/focus-red.uf2), [Green Boards](/docs/firmware/download/focus-green.uf2) and [Blue Boards](/docs/firmware/download/focus-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/focus/)

The Athlete
-----------

**Required Mod:** Countdown timer requires soldering the buzzer connector.

For folks who want to use the watch for fitness.

* Simple Clock - A basic clock with date for timekeeping.
* Stopwatch (by Wesley Ellis) - It counts up.
* Countdown (by Wesley Ellis) - It counts down.
* Exercise Counter (by Shogo Okamoto) - Designed for tracking a number of exercises by pressing the Alarm button.
* Pulsometer - Hold the Alarm button while touching a vein on your neck, and count 30 beats. Release for your heart rate.

Download it now: for [Red Boards](/docs/firmware/download/the_athlete-red.uf2), [Green Boards](/docs/firmware/download/the_athlete-green.uf2) and [Blue Boards](/docs/firmware/download/the_athlete-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/the_athlete/)

The Backpacker
--------------

**Required Sensor Board:** Temperature Sensor

This watch face is focused on helping you when out in the backcountry.

* Simple Clock - A basic clock with date for timekeeping.
* Sunrise/Sunset - Local sunrise and sunset times. Don't get caught in the dark!
* Moon Phase - Tonight's moon phase. For when the sun fails you.
* Temperature - As measured from the temperature sensor board. (Alarm button toggles C or F)
* Temperature Log - A 36-hour log. Toss the watch outside your tent to measure overnight lows.
* Blinky Light - This will chew through your battery, but could be useful in an emergency.

Download it now: for [Red Boards](/docs/firmware/download/the_backpacker-red.uf2), [Green Boards](/docs/firmware/download/the_backpacker-green.uf2) and [Blue Boards](/docs/firmware/download/the_backpacker-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/the_backpacker/)

The Stargazer
-------------

For folks who think space is the place!

* Simple Clock - A basic clock with date for timekeeping.
* Astronomy - Calculates altitude, azimuth, right ascension and declination for all planets
* Sunrise/Sunset - Local sunrise and sunset times.
* Moon Phase - Today's moon phase. (press Alarm to see days in the future)

Download it now: for [Red Boards](/docs/firmware/download/the_stargazer-red.uf2), [Green Boards](/docs/firmware/download/the_stargazer-green.uf2) and [Blue Boards](/docs/firmware/download/the_stargazer-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/the_stargazer/)

Deep Space Now
--------------

For folks who work in deep space. (no, really!)

* Simple Clock - A basic clock with date for timekeeping.
* Mars Time - Displays Mars Standard Time, or local mean solar time and mission sol for each active mission on Mars.
* World Clock - One slot for the ground station in Goldstone (California, USA)
* World Clock - One slot for the ground station in Madrid (Spain)
* World Clock - One slot for the ground station in Canberra (Australia)
* Day One - Counts the number of days from a given date. Try plugging in the start of a mission (i.e. August 20, 1977) to get mission day.

Download it now: for [Red Boards](/docs/firmware/download/deep_space_now-red.uf2), [Green Boards](/docs/firmware/download/deep_space_now-green.uf2) and [Blue Boards](/docs/firmware/download/deep_space_now-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/deep_space_now/)

alt.time
--------

For fans of alternative timekeeping systems.

* Simple Clock - A basic clock with date for timekeeping.
* Beat Time (by Wesley Ellis) - AKA Swatch Internet Time, a decimal time standard centered on Switzerland.
* Day One - Counts the number of days from a given date. Try plugging in your birthday!

I hope to expand this face in the future. (International Fixed Calendar, anyone?)

Download it now: for [Red Boards](/docs/firmware/download/alt_time-red.uf2), [Green Boards](/docs/firmware/download/alt_time-green.uf2) and [Blue Boards](/docs/firmware/download/alt_time-blue.uf2)

Try it out: [Sensor Watch Emulator](/docs/firmware/simulate/alt_time/)
