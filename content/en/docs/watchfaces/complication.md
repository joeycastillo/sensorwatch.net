---
title: "Complications"
linkTitle: "Complications"
weight: 8
---
In horology, a complication is an additional set of gears in a mechanical watch movenent that enables a secondary function, such as a sunrise/sunset dial. The watch faces in this category do just that.

 * [Sunrise/Sunset](#sunrisesunset)
 * [Moon Phase](#moon-phase)
 * [Stopwatch](#stopwatch)
 * [Stock Stopwatch](#stock-stopwatch)
 * [Countdown](#countdown)
 * [Timer](#timer)
 * [Counter](#counter)
 * [Interval](#interval)
 * [Alarm](#alarm)
 * [Pulsometer](#pulsometer)
 * [Tomato Productivity Timer](#tomato-productivity-timer)
 * [TOTP Generator](#totp-generator)
 * [Day One](#day-one)
 * [Time Left](#time-left)
 * [Blinky Light](#blinky-light)
 * [Astronomy](#astronomy)
 * [Orrery](#orrery)
 * [Invaders](#invaders)
 * [RPN Calculator](#rpn-calculator)

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

The Stopwatch face provides basic stopwatch functionality: you can start and stop the stopwatch with the alarm button. Pressing the light button when the timer is stopped resets it. This face does not count sub-seconds.

Stock Stopwatch
---------------

The Stock Stopwatch face implements the original F-91W stopwatch functionality, including counting hundredths of seconds and lap timing. 
* Use the alarm button to start and stop the stopwatch.
* Press the light button while the stopwatch is running to view the lap time. The stopwatch continues running in the background, indicated by a blinking colon.
* Press the light button again to switch back to the running stopwatch.
* Press the light button when the timekeeping is stopped to reset the stopwatch.

There are two improvements compared to the original F-91W: 
1. When the stopwatch reaches 59:59, the counter does not simply jump back to zero but keeps track of hours in the upper right-hand corner (up to 24 hours).
2. Long-press the light button to toggle the LED behavior. It either turns on with each button press or remains off.

Countdown
---------

TODO

Timer
-----

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

Counter
-------

TODO

Interval
--------

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

Alarm
-----

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


Day One
-------

This watch face displays the number of days since a given date. It was originally designed to display the number of days you've been alive, but technically it can count up from any date in the 20th century or the 21st century, so far.

Long press on the Alarm button to enter customization mode. The text "YR" will appear, and will allow you to set the year starting from 1959. Press Alarm repeatedly to advance the year. If your birthday is before 1959, advance beyond the current year and it will wrap around to 1900. Once you have set the year, press Light to set the month ("MO") and day ("DA"), advancing the value by pressing Alarm repeatedly.

Note that at this time, the Day One face does not display the sleep indicator in sleep mode, which may make the watch appear to be unresponsive in sleep mode. You can still press the Alarm button to wake the watch. This UI quirk will be addressed in a future update.

Time Left
---------

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

Once you've selected the celestial body whose parameters you wish to calculate, long press the Alarm button and release it. The letter “C” will flash while the calculation is performed.

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

Invaders
--------

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


RPN Calculator
--------------

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

