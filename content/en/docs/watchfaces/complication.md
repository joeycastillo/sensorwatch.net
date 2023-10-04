---
title: "Complications"
linkTitle: "Complications"
weight: 8
---
In horology, a complication is an additional set of gears in a mechanical watch movenent that enables a secondary function, such as a sunrise/sunset dial. The watch faces in this category do just that.

 * [Activity](#activity)
 * [Alarm](#alarm)
 * [Astronomy](#astronomy)
 * [Blinky Light](#blinky-light)
 * [Breathing](#breathing)
 * [Countdown](#countdown)
 * [Counter](#counter)
 * [Databank](#databank)
 * [Day One](#day-one)
 * [Disc golf](#disc-golf)
 * [Dual timer](#dual-timer)
 * [Flashlight](#flashlight)
 * [Geomancy](#geomancy)
 * [Habit](#habit)
 * [Interval](#interval)
 * [Invaders](#invaders)
 * [Moon Phase](#moon-phase)
 * [Morse Calculator](#morse-calculator)
 * [Orrery](#orrery)
 * [Planetary Hours](#planetary-hours)
 * [Planetary Time](#planetary-time)
 * [Probability](#probability)
 * [Pulsometer](#pulsometer)
 * [Randonaut](#randonaut)
 * [Rate Meter](#rate-meter)
 * [RPN Calculator](#rpn-calculator)
 * [RPN Calculator Alternate](#rpn-calculator-alternate)
 * [Sailing](#sailing)
 * [Ship's bell](#ships-bell)
 * [Stock Stopwatch](#stock-stopwatch)
 * [Stopwatch](#stopwatch)
 * [Sunrise/Sunset](#sunrisesunset)
 * [Tachymeter](#tachymeter)
 * [Tally](#tally)
 * [Tarot](#tarot)
 * [Temperature Chart](#temperature-chart)
 * [Time Left](#time-left)
 * [Timer](#timer)
 * [Tomato Productivity Timer](#tomato-productivity-timer)
 * [Toss Up](#toss-up)
 * [TOTP Generator](#totp-generator)
 * [TOTP Generator LFS](#totp-generator-lfs)

Activity
--------
[`activity_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/activity_face.h)

The Activity face lets you record activities like you would do with a fitness watch.
It supports different activities like running, biking, rowing etc., and for each recorded activity
it stores when it started and how long it was.

You can save up to 99 activities this way. Every once in a while you can chirp them out
using the watch's piezo buzzer as a modem, then clear the log in the watch.
To record and decode a chirpy transmission on your computer, you can
[use the web app here](https://jealousmarkup.xyz/off/chirpy/rx/).

### Using the face

When you activate the face, it starts with the first screen to select the activity you want to log.
ALARM cycles through the list of activities.
LONG ALARM starts logging.
While logging is in progress, the face alternates between the elapsed time and the current time.
You can press ALARM to pause (e.g., while you hop in to the baker's for a croissant during your jog).
Pressing ALARM again resumes the activity.
LONG ALARM stops logging and saves the activity.

When you're not loggin, you can press LIGHT to access the secondary faces.
LIGHT #1 => Shows the size of the log (how many activities have been recorded).
LIGHT #2 => The screen to chirp out the data. Press LONG ALARM to start chirping.
LIGHT #3 => The screen to clear the log in the watch. Press LONG ALARM twice to clear data.

### Quirky details

The face will discard short activities (less than a minute) when you press LONG ALARM to finish logging.
These were probably logged by mistake, and it's better to save slots and chirping battery power for
stuff that really matters.

The face will continue to record an activity past the normal one-hour mark, when the watch
enters low energy mode. However, it will always stop at 8 hours. If an activity takes that long,
you probably just forgot to stop logging.

The log is stored in regular memory. It will be lost when you remove the battery, so make
sure you chirp it out before taking the watch apart.

See the top of activity_face.c for some customization options. What you most likely want to do
is reduce the list of activities shown on the first screen to the ones you are regularly doing.

Alarm
-----
[`alarm_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/alarm_face.h)

The Alarm face implements 16 customizable alarms on the sensor watch.

Usage:
- In normal mode, the alarm button cycles through all 16 alarms. 
- Pressing the alarm button long in normal mode toggles the corresponding alarm on or off.\
(Whereas pressing the alarm button extra long jumps back to the first alarm.)
- Pressing the light button enters settings mode and cycles through the settings of each alarm.\
(Long pressing the light button enters settings mode without illuminating the led.)
- In settings mode an alarm slot is selected by pressing the alarm button when the slot number 
in the upper right corner is blinking.
- For each alarm slot, you can select the day. These are the day modes:
   - ED = the alarm rings every day
   - 1t = the alarm fires only one time and is erased afterwards
   - MF = the alarm fires Mondays to Fridays
   - WN = the alarm fires on weekends (Sa/Su)
   - MO to SU = the alarm fires only on the given day of week
- You can fast cycle through hours or minutes by holding the alarm button.
- You can select the tone in which the alarm is played. (Three pitch levels available.)
- You can select how many "beep rounds" are played for each alarm. 1 to 9 rounds, plus extra 
long ('L') and extra short ('o') alarms.
- The simple watch face indicates if any alarm is set within the next 24h by showing the signal
indicator.

Astronomy
---------
[`astronomy_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/astronomy_face.h)

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

Once you've selected the celestial body whose parameters you wish to calculate, long press the Alarm button and release it. The letter “C” will flash while the calculation is performed.

When the calculation is complete, the screen will display the altitude (“aL”) of the celestial body. You can cycle through the available parameters with repeated short presses on the Alarm button:

* aL - Altitude (in degrees), the elevation over the horizon. If negative, it is below the horizon.
* aZ - Azimuth (in degrees), the cardinal direction relative to true north.
* rA - Right Ascension (in hours/minutes/seconds)
* dE - Declination (in degrees/minutes/seconds)
* di - Distance (the digits in the top right will display either aU for astronomical units, or K for kilometers)

Long press on the Alarm button to select another celestial body.

Blinky Light
------------
[`blinky_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/blinky_face.h)

The blinky light watch face was designed as a tutorial for making a watch face in Movement, but it actually might be useful to have a blinking light in a pinch.

The screen displays the name of the watch face (”BL”), as well as an S at the top right for slow blink or an F for fast blink. The bottom line selects the color: green, red or yellow. You can change the speed of the blinking light by pressing the Alarm button, and change the color with the Light button. A long press on the Alarm button starts the blinking light, and another long press stops it.

**Note that this will chew through your battery!** The green LED uses about 450µA at full brightness, which is 45 times the normal power consumption of the watch. The red LED is an order of magnitude less efficient (4500 µA), and the yellow setting lights both LEDs, which chews through nearly 5 milliamperes. This means that one hour of yellow blinking is likely to eat up between 2 and 3 percent of the battery's usable life! Still, if you need to signal your location to someone in a dark forest, this watch face could come in handy.

Just try to use the green LED as much as you can.

Breathing
---------
[`breathing_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/breathing_face.h)

Breathing is a complication for guiding boxed breathing sessions.
Boxed breathing is a technique to help you stay calm and improve
concentration in stressful situations.

Usage: Timed messages will cycle as long as this face is active.
Press ALARM to toggle sound.

Countdown
---------
[`countdown_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/countdown_face.h)

Slight extension of the original countdown face by Wesley Ellis.
  - Press the light button to enter setting mode and adjust the
    countdown timer.
  - Start and pause the countdown using the alarm button, similar
    to the stopwatch face.
  - When paused or terminated, press the light button to restore the
    last entered countdown.

Max countdown is 23 hours, 59 minutes and 59 seconds.

Note: we have to prevent the watch from going to deep sleep using
movement_schedule_background_task() while the timer is running.

Counter
-------
[`counter_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/counter_face.h)

Counter face is designed to count the number of running laps during exercises.

Usage:
Short-press ALARM to increment the counter (loops at 99)
Long-press ALARM to reset the counter.
Long-press LIGHT to toggle sound.

Databank
--------
[`databank_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/databank_face.h)

Displays some pre-defined data that you might want to remember
Math constants, birthdays, phone numbers...

Usage: Edit the global variable `pi_data` in "databank_face.c"
to the define the data that will be displayed. Each "item" contains
a two-letter label (using the day-of-week display), then a longer
string that will be displayed one "word" (six characters) at a time.

Short-press ALARM to display the next word.
Short-press LIGHT to display the previous word.
Long-press ALARM to display the next item.
Long-press LIGHT to display the previous item.

Day One
-------
[`day_one_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/day_one_face.h)

This watch face displays the number of days since a given date. It was originally designed to display the number of days you've been alive, but technically it can count up from any date in the 20th century or the 21st century, so far.

Long press on the Alarm button to enter customization mode. The text "YR" will appear, and will allow you to set the year starting from 1959. Press Alarm repeatedly to advance the year. If your birthday is before 1959, advance beyond the current year and it will wrap around to 1900. Once you have set the year, press Light to set the month ("MO") and day ("DA"), advancing the value by pressing Alarm repeatedly.

Note that at this time, the Day One face does not display the sleep indicator in sleep mode, which may make the watch appear to be unresponsive in sleep mode. You can still press the Alarm button to wake the watch. This UI quirk will be addressed in a future update.

Disc Golf
---------
[`discgolf_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/discgolf_face.h)

 * Keep track of scores in discgolf or golf!
 * The watch face operates in three different modes:
 *
 *  - dg_setting: Select a course
 *      Enter this mode by holding down the light button. The screen will display
 *      the label for the hole and the lowest score since last boot.
 *      Press alarm to loop through the holes. Press the light button to make a
 *      selection. This will reset all scores and start a new game in dg_idle mode.
 *
 *  -dg_idle: We're playing a hole
 *      This either shows your current score relative to par, or the score for a
 *      particular hole.
 *      At the start of a game, press alarm to loop through the holes and leave it
 *      your starting hole. For optimal experience, play the course linearly after that
 *      If you're viewing the hole you're supposed to be playing, the watch face will
 *      display your score relative to par.
 *      Use the alarm button to view other holes than the one you're playing, in which
 *      case the input score for that hole will be displayed, in case it needs changing.
 *      Long press the alarm button to snap back to currently playing hole.
 *      To input scores for a hole in this mode, press the light button.
 *
 *  -dg_scoring: Input score for a hole
 *      In this mode, if the score is 0 (hasn't been entered during this round),
 *      it will blink, indicating we're in scoring mode. Press the alarm button
 *      to increment the score up until 15, in which case it loops back to 0.
 *      Press the light button to save the score for that hole, advance one hole
 *      if you're not editing an already input score, and returning to idle mode.
 *
 *  When all scores have been entered, the LAP indicator turns on. At that point, if we enter
 *  dg_setting to select a course, the score for that round is evaluated against the current
 *  lowest score for that course, and saved if it is better.

Dual Timer
----------
[`dual_timer_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/dual_timer_face.h)

Inspired by special ops and tactical trope targeted watches like the Nixon Regulus
that feature two chronographs for timing two simultaneous events, here is a watch
face that expands upon Andreas Nebinger's Stock Stopwatch Face code to implement this 
functionality.

ALARM starts/stops timer A, resets on the next start
LIGHT starts/stops timer B, resets on the next start

When a timer is running, tapping MODE toggles between displaying timers A or B, as
indicated at the top of the display.

The currently selected timer shows minutes, seconds, and 100ths of seconds until the
timed event passes the hour mark. Then it shows hours, minutes, and seconds. Once
it runs for more than a day it shows days, hours, and minutes. The blinking colon
indicates that the timer is running.

The longest time span the timers are able to track as 99 days and 23:59:59:99 hours and
they will simply stop.

If the other timer that is not currently selected is also running then a plus sign is
blinking next to the A or B indicator. Its progress is indicated by showing the timer's
currently highest time unit ( 100ths of seconds if less than a second, seconds if less
than a minute, minutes if less than an hour, hours if less than a day, days if more than
a day).

Please Note: If at least one timer is running then the default function of the MODE
button to move to the next watch face is disabled to be able to use it to toggle between
the timers. In this case LONG PRESSING MODE will move to the next face instead of moving
back to the default watch face.

IMPORTANT: This watch face uses the same TC2 callback counter as the Stock Stopwatch
watch-face. It works through calling a global handler function. The two watch-faces
therefore can't coexist within the same firmware. If you want to compile this watch-face
then you need to remove the line <../watch_faces/complication/stock_stopwatch_face.c \>
from the Makefile.

Flashlight
----------
[`flashlight_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/flashlight_face.h)

A flashlight for use with the Flashlight sensor board.

When the watch face appears, the display will show "FL" in the top two positions.
Pressing the Light button will toggle the flashlight on and off.

Geomancy
--------
[`geomancy_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/geomancy_face.h)

A simple and straightforward watch face for the ancient Eastern geomantic divination system
of I Ching and the western system of "Geomancy". It is an optional addition to the Toss Up
Face.

The LIGHT button toggles between the two systems of geomancy.

The ALARM button casts an I Ching hexagram or Geomantic figure based on drawing virtual
stalks from the True Random Number Generator in the Sensor Watch.

The figures are flipped 90 degrees clockwise, so the left side is the bottom and the
right side the top.

LONG PRESSING ALARM toggles the display of the King Wen sequence index for the cast I Ching
Hexagram (https://en.wikipedia.org/wiki/King_Wen_sequence )or the abbreviated name for the
cast Geomantic Figure:

GF - Greater Fortune (Fortuna Major)
LF - Lesser Fortune (Fortuna Minor)
PO - Populus
VI - Via
AL - Albus
CO - Conjunctio
PA - Puella
AM - Amissio
PR - Puer
RU - Rubeus
AQ - Acquisitio
LA - Laetitia
TR - Tristitia
CA - Carcer
HD - Head of the Dragon (Caput Draconis)
TD - Tail of the Dragon (Cauda Draconis)

Habit
-----
[`habit_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/habit_face.h)

Allows the user to record a single succesful instance of a particular habit
occuring per day, and displays history for eight days prior as well as a
total counter.

Interval
--------
[`interval_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/interval_face.h)

The Interval face provides 9 customizable interval timers, which can be used for hit training and/or time management techniques.

- To cycle through the 9 interval timers, press the alarm button (short press). For each timer slot, the relevant details for each timer phase are shown in a "carousel" (see below).

- To start an interval timer, press and hold the alarm button.

- To pause a running timer, press the alarm button (short press).

- To completely abort a running timer, press and hold the alarm button.

- Press and hold the light button to enter settings mode for the current interval timer. Short pressing the light button cycles through the settings of each timer.

- Each interval timer has 1 to 4 phases of customizable length like so:\
`(1) prepare/warm up --> (2) work --> (3) break --> (4) cool down`\
When setting up or running a timer, each of these phases is indicated by the letters "PR" (prepare), "WO" (work), "BR" (break), or "CD" (cool down).

- Each of these phases is optional, and you can set the corresponding minutes and seconds to zero. If you want to use the timer, at least one phase needs to be set to a non-zero value.

- You can define the number of rounds either only for the work phase and/or for the combination of work + break phase. Let's say you want an interval timer that counts 3 rounds of 30 seconds work, followed by 20 seconds rest, like so:\
    *work 30s* --> *work 30s* --> *work 30s* --> *break 20s*\
You can do this by setting 30s for the "WO"rk phase and setting a 3 in the lower right-hand corner of the work page. The "LAP" indicator lights up at this position, to explain that we are setting laps here. After that, set the "BR"eak phase to 20s and leave the rest as it is.

- If you want to set up a certain number of "full rounds", consisting of work phase(s) plus breaks, you can do so at the "BR"eak page. The number in the lower right-hand corner determines the number of full rounds to be counted. A "-" means that there is no limit, and the timer keeps alternating between work and break phases.

- This watch face comes with several pre-defined interval timers suitable for HIIT training (timer slots 1 to 4) as well as doing work according to the Pomodoro technique (timer slots 5 to 6). Feel free to adjust the timer slots to your own needs (or completely wipe them).

Invaders
--------
[`invaders_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/invaders_face.h)

The Invaders watch face is an authentic remake of the "famous" number invaders game, found on the Casio calculator wristwatches CA-85 or CA-851.

How to play:

- Press the alarm button to start the game. "Invaders" (just digits, tbh) will start coming in from the right-hand side.
- Press the light button to "aim". The digit on the top of the display cycles from 0 to 9. 
- If your aiming digit is identical to one of the invaders, press the alarm button to "shoot". The corresponding invader will disappear.
- If the invaders reach beneath the very first position, you loose one defense line. When all three defense lines are gone, the game is over.
- Also: If you shoot more than 29 times per wave, you lose the game.
- There are 16 invaders per wave. There is a short break between waves.
- Long pressing the light button toggles sound on or off (not while playing).

The "n" invaders are ufos!

Whenever the sum of all invaders shot is divisible by 10 the next invader will be an ufo, represented by the n-symbol. Shooting a ufo gets you extra points. Example: shoot 2, 5, 3 --> ufo next

As for points: the earlier you shoot an invader, the more points you get.

To anyone interested in the original game manual, see here: [https://www.digitalwatchlibrary.com/images/casio_manuals/0134.pdf](https://www.digitalwatchlibrary.com/images/casio_manuals/0134.pdf)

Moon Phase
----------
[`moon_phase_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/moon_phase_face.h)

The Moon Phase face is similar to the Sunrise/Sunset face: it displays the current phase of the moon, along with the day of the month and a graphical representation of the moon on the top row.

This graphical representation is a bit abstract. The segments that turn on represent the shape of the moon, waxing from the bottom right and waning at the top left. A small crescent at the bottom right will grow into a larger crescent, then add lines in the center for a quarter and half moon. All segments are on during a full moon. Then gradually the segments at the bottom right will turn off, until all that remains is a small waning crescent at the top left.

All segments turn off during a new moon.

On this screen you may press the Alarm button repeatedly to move forward in time: the day of the month at the top right will advance by one day for each button press, and both the text and the graphical representation will display the moon phase for that day. Try pressing the Alarm button 27 times now, just to visualize what the moon will look like over the next month.

Morse Calculator
----------------
[`morsecalc_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/morsecalc_face.h)

Morse-code-based RPN calculator

The calculator is operated by first composing a **token** in Morse code,
then submitting it to the calculator. A token specifies either a calculator
operation or a float value.

These two parts of the codebase are totally independent:
 1. The Morse-code reader (`mc.h`, `mc.c`)
 2. The RPN calculator (`calc.h`, `calc.c`, `calc_fn.h`, `calc_fn.c`, `small_strtod.c`)

The user interface (`morsecalc_face.h`, `morsecalc_face.c`) lets you talk
to the RPN calculator through Morse code.

### Controls
 - `light` is dash
 - `alarm` is dot
 - `mode` is "finish character"
 - long-press `mode` or submit a blank token to switch faces
 - long-press `alarm` to show stack
 - long-press `light` to toggle the light

### Morse code token entry
As you enter `.`s and `-`s, the morse code char you've entered will
appear in the top center digit. At the top right is the # of morse code
`.`/`-` you've input so far. The character resets at the 6th `.`/`-`.

Once you have the character you want to enter, push `mode` to enter it.

The character will be appended to the current token, whose 6 trailing
chars are shown on the main display. Once you've typed in the token you
want, enter a blank Morse code character and then push `mode`.
This submits it to the calculator.

Special characters:
 - Backspace is `(` (`-.--.`).
 - Clear token input without submitting to calculator is `Start
   transmission` (`-.-.-`).

### Writing commands
First the calculator will try to interpret the token as a command/stack operation.
Commands are defined in `calc_dict[]` in `movement/lib/morsecalc/calc_fns.h`.
If the command doesn't appear in the dictionary, the calculator tries to interpret the token as a number.

### Writing numbers
Numbers are written like floating point strings.
Entering a number pushes it to the top of the stack if there's room.
This can get long, so for convenience numerals can also be written in binary with .- = 01.

    0   1    2    3    4    5    6    7    8    9
    .   -    -.   --   -..  -.-  --.  ---  -... -..-
    e   t    n    m    d    k    g    o    b    x

 - Exponent signs must be entered as "p".
 - Decimal place "." can be entered as "h" (code ....)
 - Sign "-" can be entered as "Ch digraph" (code ----)

For example: "4.2e-3" can be entered directly, or as "4h2pC3"
  similarly, "0.0042" can also be entered as "eheedn"
Once you submit a number to the watch face, it pushes it to the top of the stack if there's room.

### Number display
After a command runs, the top of the stack is displayed in this format:

  - Main 4 digits = leading 4 digits
  - Last 2 digits = exponent
  - Top middle = [Stack location, Sign of number]
  - Top right = [Stack exponent, Sign of exponent]

Blank sign digit means positive.
So for example, the watch face might look like this:

    [   0 -5]
    [4200 03]

... representing `+4.200e-3` is in stack location 0 (the top) and it's one of five items in the stack.

### Looking at the stack
To show the top of the stack, push and hold `light`/`alarm` or submit a blank token by pushing `mode` a bunch of times.
To show the N-th stack item (0 through 9):

 - Put in the Morse code for N without pushing the mode button.
 - Push and hold `alarm`.

To show the memory register, use `m` instead of a number.

To see all the calculator operations and their token aliases, see the `calc_dict[]` struct in `calc_fns.h`

Orrery
------
[`orrery_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/orrery_face.h)

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

Planetary Hours
---------------
[`planetary_hours_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/planetary_hours_face.h)

### Background

Both the 24 hour day and the order of our weekdays have quite esoteric roots.
The ancient Egyptians divided the day up into 12 hours of sunlight and 12 hours
of night time. Obviously the length of these hours varied throughout the year.

The Greeks assigned each hour a ruler of the planetary gods in the ancient
"Chaldean" order from slowest (Chronos for Saturn) to fastest (Selene for Moon).
Because 24 hours cannot be equally divided by seven, the planetary rulers carried
over to the first hour of the next day, effectively ruling over the entire day 
and lending the whole day their name. The seven day week was born.

### PLANETARY HOUR CHART COMPLICATION

This complication watch face displays the start time of the current planetary hour 
according to the given location and day of the year. The number of the current
planetary hour (1 - 24) is indicated at the top right.

Short pressing the ALARM button flips through the start times of the following 
planetary hours, long pressing it flips backwards in time. A long press of the 
LIGHT button immediately switches back to the start time of the current hour.
The Bell indicator always marks the current planetary hour in the list.
The LAP indicator shows up when the hours of the next phase are part of the 
upcoming day instead of the current one. This happens when the watch face is 
launched after sunset.

The planetary ruler of the current hour and day is displayed at the top in 
Latin or Greek shorthand notation:

Saturn (SA) / Chronos (CH) / ♄
Jupiter (JU) / Zeus (ZE) / ♃
Mars (MA) / Ares (AR) / ♂
Sol (SO) / Helios (HE) / ☉
Venus (VE) / Aphrodite (AF) / ♀
Mercury (ME) / Hermes (HR) / ☿
Luna (LU) / Selene (SE) / ☾

A short press of the LIGHT button toggles between Latin and Greek ruler shorthand
notation.

(IMPORTANT: Make sure the watch's time, timezone and location are set correctly for this
watch face to work properly!)

Planetary Time
--------------
[`planetary_time_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/planetary_time_face.h)

### BACKGROUND

Both the 24 hour day and the order of our weekdays have quite esoteric roots.
The ancient Egyptians divided the day up into 12 hours of sunlight and 12 hours
of night time. Obviously the length of these hours varied throughout the year.

The Greeks assigned each hour a ruler of the planetary gods in the ancient
"Chaldean" order from slowest (Chronos for Saturn) to fastest (Selene for Moon).
Because 24 hours cannot be equally divided by seven, the planetary rulers carried
over to the first hour of the next day, effectively ruling over the entire day 
and lending the whole day their name. The seven day week was born.

### PLANETARY TIME COMPLICATION

The hour digits of this complication watch-face display the current planetary hour 
according to the given location and day of the year (First hour from 12am to 1am,
the second hour from 1am to 2am, and so forth).

Like with normal clocks the minutes and seconds help dividing the hour into smaller
units. On this watch-face, all units naturally vary in length because the planetary
hours are not fixed by duration but by the moments of sunrise and sunset which 
obviously vary throughout the year, especially in higher latitudes.

On this watch-face the hours indicated as 12am to 12pm (00:00 - 12:00) are used for
the planetary daytime hours between sunrise and sunset and hours indicated as 12pm 
to 12am (12:00 - 00:00) are used for the planetary night hours after sunset and before 
sunrise.

The planetary ruler of the current hour and day is displayed at the top in Latin or 
Greek shorthand notation:

Saturn (SA) / Chronos (CH) / ♄
Jupiter (JU) / Zeus (ZE) / ♃
Mars (MA) / Ares (AR) / ♂
Sol (SO) / Helios (HE) / ☉
Venus (VE) / Aphrodite (AF) / ♀
Mercury (ME) / Hermes (HR) / ☿
Luna (LU) / Selene (SE) / ☾

The ALARM button toggles between displaying the ruler of the hour and the ruler of the day

The LIGHT button toggles between Latin and Greek ruler shorthand notation

(IMPORTANT: Make sure the watch's time, timezone and location are set correctly for this
watch face to work properly!)

Probability
-----------
[`probability_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/probability_face.h)

This face is a dice-rolling random number generator.
Supports dice with 2, 4, 6, 8, 10, 12, 20, or 100 sides.

Press LIGHT to cycle through die type.
The current die size is indicated on the left ("C" for 100)

Press ALARM to roll the selected die.

Pulsometer
----------
[`pulsometer_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/pulsometer_face.h)

The Pulsometer is an implementation of a sort of a classic mechanical watch complication. A [classic pulsometer complication](https://watchtime.me/news/features/article/1424/what-is-a-pulsometer-scale-7-cool-doctor-s-watches) involves a chronograph with a scale calibrated for counting a certain number of heartbeats (often 30). You start it and begin counting heartbeats, and stop it after counting the specified number of beats. Once stopped, the needle will point to your heart rate.

The pulsometer on Sensor Watch flashes its instructions at launch: “Hold Alarm + count 30 beats.” Using the hand on the side where you wear your watch, touch your carotid artery (in your neck) and feel for your pulse. Once you find it, use your other hand to press and hold the Alarm button, and count your heartbeats. When you reach 30 beats, release the Alarm button. The display will show a number such as “60 bpm”; this is your heart rate in beats per minute.

Two notes:

1. For the first few seconds of a measurement, the display will read “Hi”. This indicates that it's too early for the measured value to be a valid heart rate. Once the measurement is below 240 bpm, the display will update.
2. If you hold the button down for more than 45 seconds, the display will read “Lo”. If it took this long for you to count 30 heartbeats, this indicates that your heart rate is below 40 beats per minute.

Randonaut
---------
[`randonaut_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/randonaut_face.h)

Randonauting is a way to turn the world around you into an adventure and get the user outside 
of their day-to-day routine by using a random number generator to derive a coordinate to journey 
to. In Randonauts lore so-called "Blind Spots" are places you cannot reach methodologically. They
may exist in your own backyard for your whole life and you will never even notice them, because 
you simply have no reason to go to that exact place or look in its direction. Since the very 
limitations of our behavioral algorithms are the reason for the existence of blindspots, they 
can only be found using a randomizer.

This watch face generates a random location based on the watch's location and a set radius using
the official Randonautica Blind Spot algorithm.

The ALARM button starts the random location generation and then automatically displays the found
Blind Spot.

By pressing ALARM again the user can flip through different pieces of information about the Blind
Spot: Distance (DI), Bearing Degree (BE), Latitude degrees and decimal digits (LA), Longitude 
degrees and decimal digits (LO).

Pressing LIGHT switches between generating a new blind spot ("Rando") and displaying the info of
the last generated one ("Point").

LONG PRESSING LIGHT toggles setup mode. Here pressing LIGHT switches between setting the desired
radius (RA) and setting the random number generator (RNG) for generating the blind spot. 

ALARM changes the values respectively:

- The radius can be set in 500 meter steps between 1000 and 10,000 meters
- The RNG can be set to "true" which utilizes the SAML22J's internal True Random Number Generator
- Setting it to "psudo" will use the pseudorandom number generation algorithm arc4random
- Setting it to "chance" will randomly chose either of the RNGs for each generation (default)

LONG PRESSING ALARM toggles DATA mode in which the currently generated Blind Spot coordinate can
be written to the <place.loc> file on the watch (press ALARM) and set as active high precision 
location used by other watch faces. It does not overwrite the low precision location information
in the watch register commonly used for astronomical watch faces.

Rate Meter
---------
[`ratemeter_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/ratemeter_face.h)

The rate meter shows the rate per minute at which the ALARM button is
being pressed. This is particularly useful in sports where cadence
tracking is useful. For instance, rowing coaches often use a dedicated
rate meter - clicking the rate button each time the crew puts their oars
in the water to see the rate (strokes per minute) on the rate meter.

RPN Calculator
--------------
[`rpn_calculator_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/rpn_calculator_face.h)

The calculator uses [RPN](https://en.wikipedia.org/wiki/Reverse_Polish_notation) notation. So instead of using infix operators, the operators always follow the parameters.

Example: To calculate `4 - 3` one would enter `4 3 -`

Using this notation also does not require any braces, so instead of `2 * (3 - 2)` one would enter `2 3 2 - *`.

The parameters are put on to a stack, which currently has a size of 4. So if one enters `2 3 2 - *` the stack would contain `2 3 2 0`. The subtraction then uses the first two values from the stack and pushes the result back on the stack, which leaves `1 2 0 0`. The multiplication then uses the next two values from the stack and pushes the end result: `2 0 0 0`.

### Normal mode

In normal mode the top of the stack is displayed (initially zero), which usually represents the result of the calculation.
- `ALARM` enters number mode
- `LIGHT` enters operator mode
- `MODE` switches to the next watch face

### Number mode

Number mode pushes a new parameter on the stack. The first four digits are whole numbers, the last two (smaller) digits are decimals.
- `LIGHT` cycles through digits
- `ALARM` increases the selected digit
- `MODE` pushes the parameter on the stack (and goes back to normal mode)

### Operation mode

Operation mode executes operations on the stack. Parameters are taken from the stack and the result is pushed back. If there aren't enough parameters on the stack, the calculator will go into error mode.

The display shows the current selected operation.
- `LIGHT` cycles through the available operations
- `ALARM` executes the selected operation (and goes back to normal mode, which will display the result)

Currently implemented operations:
- add (2 params)
- sub (2 params)
- mul (2 params)
- div (2 params)
- pow (2 params)
- sqrt (1 param)
- pi (0 params, will just push pi onto the stack)

### Error mode

An error has happened (currently only caused by too few parameters on the stack).
- `ALARM` goes back to normal mode
- `MODE` switches to the next watch face

### Example

To calculate the following equation:

`2 * (3 - 2)`

which would be the following in RPN notation:

`2 3 2 - *`

the following button presses are needed:

- `ALARM` enter number mode
- `ALARM` 1
- `ALARM` 2
- `MODE` push number, back to normal mode
- `ALARM` enter number mode
- `ALARM` 1
- `ALARM` 2
- `ALARM` 3
- `MODE` push number, back to normal mode
- `ALARM` enter number mode
- `ALARM` 1
- `ALARM` 2
- `MODE` push number, back to normal mode
- `LIGHT` enter operation mode
- `LIGHT` change operation to sub
- `ALARM` execute sub, back to normal mode
- `LIGHT` enter operation mode
- `LIGHT` change operation to mul
- `ALARM` execute mul, back to normal mode

RPN Calculator Alternate
------------------------
[`rpn_calculator_alt_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/rpn_calculator_alt_face.h)

Operations appear in the 'day' section; ALARM changes between operations when
operation is flashing. LIGHT executes current operation.

This is the alternate face because it has a non-traditional number entry system which
I call 'guess a number'. In number entry mode, the watch tries to guess which number you
want, and you respond with 'smaller' (left - MODE) or larger (right - ALARM). This means
that when you _are_ entering a number, MODE will no longer move between faces!

Example of entering the number 27
 - select the NO operation (probably unnecessary, as this is the default),
   and execute it by hitting LIGHT.
 - you are now in number entry mode; you know this because nothing is flashing.
 - Watch displays 10; you hit ALARM to say you want a larger number.
 - Watch displays 100; you hit MODE to say you want a smaller number.
 - Continuing: 50 -> MODE -> 30 -> MODE -> 20 -> ALARM -> 27
 - Hit LIGHT to add the number to the stack (and now 'NO' is flashing
   again, indicating you're back in operation selection mode).

One other thing to watch out for is how quickly it will switch into scientific notation
due to the limitations of the display when you have large numbers or non-integer values.
In this mode, the 'colon' serves at the decimal point, and the numbers in the top right
are the exponent.

As with the main movement firmware, this has the concept of 'secondary' functions which
you can jump to by a long hold of ALARM on NO. These are functions to do with stack
manipulation (pop, swap, dupe, clear, size (le)). If you're _not_ on NO, a long
hold will take you back to it.

See 'functions' in "rpn_calculator_alt_face.c" for names of all operations.

Sailing
-------
[`sailing_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/sailing_face.h)

Implements a sailing timer.

Usage:

### Waiting mode:
LIGHT button enters settings
ALARM button starts the timer (sailing mode).

### Sailing mode:
ALARM button switches to next programmed start signal.
Long press on LIGHT button resets timer and enters waiting mode.
Countdown to zero, then switch to counting mode.

### Counting mode:
After the start signal (0s), the duration of the race is counted (like a stopwatch timer).
ALARM button increases the lap counter, ALARM long press resets lap counter.
Long press on LIGHT button resets timer and enters waiting mode.

### Setting mode:
ALARM button increases active (blinking) signal. Goes to 0 if upper boundary
(11 or whatever the signal left to the active one is set to) is met.
10 is printed vertically (letter o plus top segment).
ALARM button long press resets to default minutes (5-4-1-0).
LIGHT button cycles through the signals.
Long press on LIGHT button cycles through sound modes:
- Bell indicator: Sound at start (0s) only.
- Signal indicator: Sound at each programmed signal and at start.
- Bell+Signal: Sound at each minute, at 30s and at 10s countdown.
- No indicator: No sound.

Ship's Bell
-----------
[`ships_bell_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/ships_bell_face.h)

A [ship's bell](https://en.wikipedia.org/wiki/Ship%27s_bell#Simpler_system) complication.

Similar to the default hourly signal of the simple_clock_face this complication will use the buzzer to signal
the time in half-hour intervals according to the scheme mentioned above.

Additionally, the user can specify one of the three watches
of the standard merchant watch system to only receive signals during this watch.

If no watch is specified all signals are emitted.

Usage:
  - short press Alarm button: Turn on/off bell
  - long press Alarm button: Cycle through the watches (All/1/2/3)

Stock Stopwatch
---------------
[`stock_stopwatch_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/stock_stopwatch_face.h)

The Stock Stopwatch face implements the original F-91W stopwatch functionality, including counting hundredths of seconds and lap timing. 
* Use the alarm button to start and stop the stopwatch.
* Press the light button while the stopwatch is running to view the lap time. The stopwatch continues running in the background, indicated by a blinking colon.
* Press the light button again to switch back to the running stopwatch.
* Press the light button when the timekeeping is stopped to reset the stopwatch.

There are two improvements compared to the original F-91W: 
1. When the stopwatch reaches 59:59, the counter does not simply jump back to zero but keeps track of hours in the upper right-hand corner (up to 24 hours).
2. Long-press the light button to toggle the LED behavior. It either turns on with each button press or remains off.

Stopwatch
---------
[`stopwatch_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/stopwatch_face.h)

The Stopwatch face provides basic stopwatch functionality: you can start and stop the stopwatch with the alarm button. Pressing the light button when the timer is stopped resets it. This face does not count sub-seconds.

Sunrise/Sunset
--------------
[`sunrise_sunset_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/sunrise_sunset_face.h)

This watch face displays local sunrise and sunset times. During the day, it displays today's sunset; at night, it displays tomorrow's sunrise.

When you first see this watch face, it will display “No Loc”, or No Location. This is because your latitude and longitude are required to calculate sunrise and sunset. When on this screen, you can set your location in a similar way to the World Clock screen.

Press and hold Alarm to enter location setting mode. The top line will read “LA” (Latitude), and the bottom line “+ 0000”. The large digits are the whole number part of the latitude, and the smaller digits (in the seconds place) are the fractional part. Enter your latitude and longitude (“LO”) by pressing the Alarm button to change the sign or advance the digits, and the Light button to move to the next character; for example, a latitude of 40.73° N would be “+ 40<small>73</small>”, and a longitude of 73.94° W would be “–073<small>94</small>”.

Once you have set your latitude and longitude, the Sunrise/Sunset face will display the next sunrise or sunset on the bottom row, and the day of that sunrise or sunset at the top right.

A short press on the Alarm button will advance to the following sunrise or sunset: for example, on Monday afternoon, it will display Monday evening’s sunset, but a short press on the Alarm button will display Tuesday morning’s sunrise.

If you made a mistake while entering your location, or if you simply wish to change your location, you can re-enter location setting mode with another long press on the Alarm button.

Tachymeter
----------
[`tachymeter_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/tachymeter_face.h)

The Tachymeter complication emulates the tachymeter function often
present in watches, that computes the average speed in [units per hour]
for a given distance given in [units].

Use case:
* User sets the distance
* User starts the tachymeter when the trip begins
* User stops the tachymeter when the trip ends
* The watch presents the average speed and trip duration in seconds

Usage:
* Go to tachymeter face, TC is shown in the Weekday Digits
* A steady d in the Day Digits indicates the distance to be used.
    * To edit the distance:
    * Long-press the Alarm button, the distance edition page (d will blink)
    * Use the Light button to change the editing (blinking) digit, and press Alarm to increase its value
    * Once done, long-press the Alarm button to exit the distance edition page
* Press the Alarm button to start the tachymeter.
    * A running animation will appear in the Day Digits
* Press the Alarm button to stop the tachymeter
* The average speed and total time information will alternate.
    * The average speed will be shown alongside /h in the Day Digits; and the total time will be shown alongside t in the Day Digits.
* Long press the Light button to return to the distance d page, and restart the tachymeter from there.
* Long-press the light button in the steady distance page to reset the distance to 1.00

Pending design points
* movement_request_tick_frequency(4) is used to obtain a 4Hz ticking, thus
  having a time resolution of 250 ms. Not sure if using event.subsecond`
  is the proper way to get the fractions of second for the start and
  final times.
* For distance and average speed, the Second Digits (position 8 and 9)
  can be seen as decimals, thus possible to show distances as short as
  0.01 km (or miles) and speeds as low as 0.01 km/h (or mph). However,
  if the same idea is used for the total time (showing hundredths),
  this limits the display to 9999.99 seconds (~2h:45m).

Tally
-----
[`tally_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/tally_face.h)

Tally face is designed to act as a tally counter.
Based on the counter_face watch face by Shogo Okamoto.

To advance the counter, press the ALARM button.
To reset, long press the ALARM button.

Tarot
-----
[`tarot_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/tarot_face.h)

Draw from a deck of tarot cards. Can choose between major arcana only or
entire deck.

In tarot reading, a card orientation can be upright or inverted, and the
interpertation of the card can change depending on this state. This face
lights the alarm indicator to show when a card is inverted. Just ignore it
if you prefer not to deal with card inversions.

This face uses the terms "Wands", "Cups", "Swords" and "Coins" for the four
suits, and numbers to represent the 14 ranked cards, with the cards 11-14
representing the Page, the Knight, the Queen, and King respectively.

Default draw is a 3-card major arcana spread.

To make it easier to keep track of where you are in the list of drawn cards,
after drawing, "St" is shown for the 1st card in the spread and "En" is
shown for the last card.

At any point, the mode button can be held to return to your first configured
watch face.

When "Major" or "All" is shown:
- Light button: cycle # of cards to draw
- Light button (long press): toggle between major arcana and all cards
- Alarm button: shuffle deck and draw cards

After cards are drawn/showing:
- Light button: view the next drawn card
- Alarm button: shuffle and re-draw new cards
- Light button (long press): go back to Draw screen, for choosing different draw parameters.

Temperature Chart
-----------------
[`tempchart_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/tempchart_face.h)

Gathers temperature statistics in a chart form.
Statistics bins are per hour / per 0.5°C.

Saved to file every day at 00:00.
Can help improve watch precision in the future. 

If you can gather statistics over few months, and then send "tempchart.ini"
to [3@14.by](mailto:3@14.by), it will help future generations of precision quartz watches.

Time Left
---------
[`time_left_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/time_left_face.h)

The Time Left Face helps you visualize how far you have progressed in a certain time span. Similar to the Day One Face, you can set your starting date. Additionally, you can also set your target or destination date. You can then use the face to display your progress in various ways.

**Usage:**

- Long-pressing of the light button starts the **settings mode**:
  - First, you set the beginning date (indicated by a 'b' in the upper right corner).
  - Begin by setting the year (indicated by the letter 'YR'). Use the alarm button to cycle through the values. Short-pressing the light button brings you to the next settings page.
  - Set the values in this order:
      1. beginning date (indicated by a 'b'): year - month - day
      2. destination date (indicated by a 'd'): year - month - day
  - After cycling through all settings pages, the face returns to display mode.

- In **display mode**, use the alarm button (short press) to cycle through these four types of display:
    1. number of days left ('DL') until the destination date is reached.
    2. remaining days expressed as a percentage of the total time span. The value is shown with two decimals, using the colon as a decimal point.
    3. number of days passed ('DA') since the beginning date. (This is the same value the Day One Face would give you.)
    4. number of days passed expressed as a percentage of the total time span.

**What is this for?**

You can use this watch face to be reminded of any kind of progress between a set start and end date. The brave among us can use it as a kind of memento mori visualization. Set your date of birth and look up the average life expectancy of  your age cohort based on publicly available mortality tables. Then, set the  statistically expected day of death as the target date, and you will be able to  see how much of your time has passed and how much is still to come.

Timer
-----
[`timer_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/timer_face.h)

The timer watch face is an advanced countdown face, providing the functionality of starting a countdown by choosing one out of nine programmable timer presets. A timer/countdown can be 23 hours, 59 minutes, and 59 seconds max. A timer can also be set to auto-repeat, which is indicated by the lap indicator.

How to use in NORMAL mode:
  - Short-pressing the alarm button cycles through all preset timer lengths. Find the current timer slot number in the upper right-hand corner.
  - Long-pressing the alarm button starts the timer.
  - Long-pressing the light button initiates settings mode.

How to use in SETTINGS mode:
  - There are up to nine slots for storing a timer setting. The current slot is indicated by the number in the upper right-hand corner.
  - Short-pressing the light button cycles through the settings values of each timer slot in the following order:  
  *hours* -> *minutes* -> *seconds* -> *timer repeat*
  - Short-pressing the alarm button alters the current settings value.
  - Long-pressing the light button returns to normal mode.

Tomato Productivity Timer
-------------------------
[`tomato_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/tomato_face.h)

Add a "tomato" timer watch face that alternates between 25 and 5 minute
timers as in the [Pomodoro Technique](https://en.wikipedia.org/wiki/Pomodoro_Technique).

The top right letter shows mode (f for focus or b for break).
The bottom right shows how many focus sessions you've completed.
(You can reset the count with a long press of alarm)

When you show up and it says 25 minutes, you can start it (alarm),
 switch to 5 minute (light) mode or leave (mode).

When it's running you can reset (alarm), or leave (mode).

When it's done, we beep and go back to step 1, changing switching
 mode from focus to break (or break to focus)

Toss Up
-------
[`toss_up_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/toss_up_face.h)

Playful watch face for games of chance or divination using coins or dice.

LIGHT switches between Coins and Dice mode

### COINS

ALARM tosses a coin. If it lands on heads it gets sorted to the left side of the
display, if it lands on tails then sorted to the right side.

LONG PRESSING ALARM adds up to 5 more coins to the toss for more nuance in the decision
making (e.g. three heads vs two tails could be read as "yes, but with serious doubts").

LONG PRESSING LIGHT flips through additional style for the coins from the default Ө/O 
to H/T (heads/tails), Y/N (yes/no), E/Ǝ, C/Ↄ

LONG PRESSING ALARM on the "Coins" title page resets to one coin.
LONG PRESSING LIGHT on the "Coins" title page resets the style to Ө/O

### DICE

ALARM rolls a six sided dice.

LONG PRESSING ALARM adds up to 2 more dice to the roll.

LONG PRESSING LIGHT flips through other available polyhedral dice types with less or more
than the default 6 sides. The options are D2, D4, D6, D8, D10, D12, D20, D24, D30, D32, D36, 
D48, and a hypothetical D99. 

When more than one dice is used for a roll this changes only the last added dice. (see Note
below)

LONG PRESSING ALARM on the "Dice" title page resets to one dice.
LONG PRESSING LIGHT on the "Dice" title page resets the dice to D6.

Please Note: If you need let's say a D8, D12, and D20 for your rolls then the procedure to
set this up would be as follows: from the default screen where you can roll the one D6 dice 
you would LONG PRESS LIGHT a few times to change the D6 to a D8, then LONG PRESS ALARM to add 
a second dice, LONG PRESS LIGHT again until the second dice changes to D12, then LONG PRESS
ALARM to add the third dice and LONG PRESS LIGHT again a few times until it becomes a D20.

TOTP Generator
--------------
[`totp_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/totp_face.h)

This watchface generates time based one time passwords (two factor auth codes) allowing you to sign in securely to many popular websites (e.g. Google, GitHub). Time-based one-time password (TOTP) is a computer algorithm that generates a one-time password (OTP) that uses the current time as a source of uniqueness.

Press the Alarm button to cycle between your configured websites / TOTP secrets.

The watchface supports multiple websites / TOTP secrets, which need to be extracted from TOTP QR codes and added to the source code for the watchface as follows:

1. Obtain a TOTP secret or QR ode from the website you want to generate codes for.
2. If you have just the QR code, [Stefan Sundin's web site](https://stefansundin.github.io/2fa-qr/) will allow you to extract the secret - it will be an alphanumeric string around 32 characters long, which is the TOTP secret encoded in Base32.
3. To add the secret to the watchface code, you need to convert it to hexadecimal bytes. This [cryptii.com](https://cryptii.com/pipes/base32-to-hex) page will allow you to do that conversion. Note you'll have to enter your TOTP secret in uppercase.
Shell tools can be used to convert secret to bytes:
```sh
echo "KRUGKIDROVUWG2ZAMJZG653OEBTG66BANJ2W24DTEBXXMZLSEB2GQZJANRQXU6JAMRXWOLQ=" | base32 -d | xxd -i
```
4. Finally, you'll need to take the Hexadecimal bytes and add them to the TOTP watchface source code and recompile movement:

### Edit `totp_face.c`
You may want to remove the demo keys. Assuming you want to add a key to the end of the list:

```
static const uint8_t num_keys = 2;
```
Add one to the number on this line.

```
static uint8_t keys[] = {
   // Add the hex bytes for your key
};
```
Add the hexadecimal bytes from step 3 to the end of this array, comma separated and each one preceeded by `0x`. Don't forget to add a comma after the previous final byte.
```
static const uint8_t key_sizes[] = {
```
Add the size of your secret (the number of hex bytes you just added) to the end of this array.
```
static const uint32_t timesteps[] = {
```
Add another `30` entry to the end of this array.
```
static const char labels[][2] = {
```
Add a label for your secret... E.g. if it's for your Google account you might want to add `{ 'g', 'o' }` as a friendly label.

That's it - enjoy the convenience of TOTP codes on your wrist!

TOTP Generator LFS
------------------
[`totp_face_lfs`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/totp_face_lfs.h)

Time-based one-time password (TOTP) generator using LFS

Reads from a file "totp_uris.txt", containing a single secret key in a
series of URLs. Each line is what's in a QR code, e.g.:
* otpauth://totp/Example:alice@google.com?secret=JBSWY3DPEHPK3PXP&issuer=Example
* otpauth://totp/ACME%20Co:john.doe@email.com?secret=HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ&issuer=ACME%20Co&algorithm=SHA1&digits=6&period=30

This is also the same as what Aegis exports in plain-text format.
This face performs minimal sanitisation of input, however.

At the moment, to get the records onto the filesystem, start a serial connection and do:
  `echo otpauth://totp/Example:alice@google.com?secret=JBSWY3DPEHPK3PXP&issuer=Example > totp_uris.txt`
  `echo otpauth://totp/ACME%20Co:john.doe@email.com?secret=HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ&issuer=ACME%20Co&algorithm=SHA1&digits=6&period=30 >> totp_uris.txt`
(note the double >> in the second one)

You may want to customise the characters that appear to identify the 2FA
code. These are just the first two characters of the issuer, and it's fine
to modify the URI.

If you have more than one secret key, press ALARM to cycle through them.

Wake
----
[`wake_face`](https://github.com/joeycastillo/Sensor-Watch/blob/main/movement/watch_faces/complication/wake_face.h)

WAKE daily alarm face

Basic daily alarm clock face. Seems useful if nothing else in the interest
of feature parity with the F-91W’s OEM module, 593.

Also experiments with caret-free UI: One button cycles hours, the other
minutes, so there’s no toggling between display and adjust modes and no
cycling the caret through the UI.

* LIGHT advances hour by 1
* LIGHT long press advances hour by 6
* ALARM advances minute by 10
* ALARM long press cycles through signal modes (just one at the moment)
