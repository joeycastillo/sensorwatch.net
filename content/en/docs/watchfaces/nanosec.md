---
title: "Calibration with Nanosec"
linkTitle: "Calibration with Nanosec"
weight: 8
---

You can include the Finetune and Nanosec faces in your Sensor Watch firmware to achieve exceptionally high accuracy within 10 seconds per year.

* [Finetune](#finetune)
* [Nanosec](#nanosec)

### Accurate timekeeping with a quartz crystal

The Sensor Watch measures time using a quartz crystal that oscillates at a frequency of 32,768 kHz. In practice, the frequency of every crystal deviates a little from the nominal value. Because the difference is very small, we don't express it as a percentage ("parts per hundred"), but as ppm ("parts per million"). For example, a deviation of +1 ppm means the frequency is 32,768.03278 kHz. This would make the watch gain about 31.5 seconds per year, because there are about 31.5 _million_ seconds in a year.

In addition to the static offset of individual crystals, their frequency also varies dynamically with temperature. Crystals are manufactured in a way that their frequency peaks at 25 °C and decreases at both higher and lower temperatures.

For accurate timekeeping, you need to correct for your crystal's static frequency offset, and your watch needs to dynamically compensate for the variation due to temperature changes. These are the things that the Nanosec and Finetune watch faces let you do.

### Calibrating the Sensor Watch

For really good results you need a watch with a temperature sensor, but you can also get a significant improvement without one. Without a temperature sensor, select correction profile P1 instead of the default P3 (details in the last section).

The firmware has to include these faces:

- A regular clock face like Simple Clock (`simple_clock_face`), because you want a way to see the time;
- Time Set (`set_time_face`), because you need a way to set the date and time;
- Finetune (`finetune_face`), so you can set the time precisely and adjust the static frequency correction;
- Nanosec (`nanosec_face`), because it contains the behind-the-scenes magic that dynamically compensates for temperature-driven variation.

To calibrate your watch, follow these steps:

1) Flash a firmware that contains the necessary faces onto the watch, assemble it, and set the time via the Time Set face.
2) Open [time.is](https://time.is) in a browser to display the accurate time. Go to the Finetune face and adjust the offset until the seconds on the watch precisely match the seconds on the screen. Apply the change without updating the frequency correction value with a long ALARM press. 

    _See the [Finetune](#finetune) section below for the details of doing this._
4) Wait a few days, then fine-tune your watch again using [time.is](https://time.is) and Finetune, saving your changes with a long LIGHT press. Your watch now knows how many hours have passed since the last time it was accurate, and how much it has drifted since then. From these two values Finetune can calculate an update to the static frequency correction value, beyond adjusting the current time itself.
5) Your watch is now a lot more accurate. Wait a few weeks until it has drifted a second or two, then repeat Step 3.
6) Wait a few months, then repeat Step 3. At this stage your Sensor Watch will be accurate to within 10 seconds per year.

Some useful details:

- You need a special site like [time.is](https://time.is) for this type of calibration. The normal time on most websites (and on most devices like laptops or smartphones) is not accurate enough.
- The Finetune face lets you adjust the time in increments of 25 msec. That is below most people's threshold of perception. You need to wait for the watch to build up a noticeable amount of drift before re-calibration is practical.
- The static frequency correction value is preserved when the watch resets. You don't need to calibrate from scratch after replacing the battery or re-flashing the firmware.
- The 10 seconds per year accuracy puts your watch right up there with the most expensive high-end quartz timekeepers.



Finetune
--------

When you reach Finetune by repeatedly pressing MODE to cycle through the installed watch faces, it will first look a little like this:

<img src="../images/finetune-01-enter.png" width="120"/>

The four 0s mean that you haven't input any time adjustment yet. The number on the right keeps updating to show the seconds part of the current time.

Finetune has two secondary faces. You need a long MODE press to move to the first of them; after that, a short press is enough.

<img src="../images/finetune-01-enter.png" width="120"/>
<img src="../images/next-mode-long.png" width="66"/>
<img src="../images/finetune-02-dt-short.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/finetune-03-6hr.png" width="120"/>

- FT means Finetune, and it's the main screen where you can enter the desired time adjustment.
- DT stands for _delta time_ and it shows the number of hours since you last adjusted the time with the Finetune face. At first you will see a small value like this because your watch hasn't been on for very long yet. The small numbers are fractional hours. E.g., the image above shows 0.05 hours, which is 3 minutes.
- F stands for frequency, and it shows the amount by which your current adjustment will update the static frequency correction value. However, unless at least 6 hours have passed, Finetune will not mess with the frequency correction, which is why at first you will see "6Hr" here.

<img src="../images/finetune-01-enter.png" width="120"/>
<img src="../images/next-light-long.png" width="66"/>
<img src="../images/finetune-04-tune-250.png" width="120"/>
<img src="../images/next-light.png" width="66"/>
<img src="../images/finetune-05-tune-275.png" width="120"/>

- Back on the main screen, you can use LIGHT and ALARM to change the adjustment. A long LIGHT press increases the offset by 250 msec; a short LIGHT press adds 25 msec.
- The first and third digits of the display have some limitations, which is why the "7" in 0275 looks a bit odd.
- You need to go towards a positive value as shown above if your watch is ahead of the true time.
- You can verify the adjustment's effect by holding your watch next to the time on an accurate clock, like [time.is](https://time.is). Your adjustment offsets the constantly ticking seconds value.

<img src="../images/finetune-01-enter.png" width="120"/>
<img src="../images/next-alarm-long.png" width="66"/>
<img src="../images/finetune-06-tune-neg250.png" width="120"/>
<img src="../images/next-alarm.png" width="66"/>
<img src="../images/finetune-07-tune-neg275.png" width="120"/>

- A long ALARM press decreases the value by 250 msec. A short ALARM press decreases it by 25 msec.
- The odd shape in the top right is meant to be a double minus sign, indicating that this is a negative adjustment.
- You need a negative adjustment if your watch is behind the true time.

Now let's see what a real calibration looks like!

<img src="../images/finetune-08-tune-1025.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/finetune-09-dt-long.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/finetune-10-corr.png" width="120"/>
<img src="../images/next-light-long.png" width="66"/>
<img src="../images/finetune-11-simple-time.png" width="120"/>

- On the FT screen I have input an offset of 1025. My watch was just a bit over a second fast.
- The DT screen tells me that 693.72 hours, or a little over four weeks, have passed since the last time I adjusted the time with Finetune.
- The F screen tells me that if I apply this adjustment, the static time correction value will increase by 0.4104 ppm. (This will make my watch about 12.9 seconds slower per year.)
- A long LIGHT press applies the adjustment to the time and updates the static time correction value. This is what I did above. Sensor Watch will be more accurate going forward!
- A long ALARM press applies the adjustment to the time but does **not** update the static frequency correction. This is what you need to do the very first time you use Finetune, when you initially set the exact time.
- After either a long LIGHT or long ALARM press on the F screen, Sensor Watch returns to the default face that shows the current time.

What if you have come to the Finetune face only to experiment but do not want to change the time, let alone mess with Sensor Watch's calibration? Easy: on the FT screen, change the value 0000 again. If you now press MODE a couple of times, Sensor Watch will move on from Finetune. Or if you just wait for a minute without pressing anything, it will return to the Simple Time screen.


Nanosec
-------

The Nanosec face has two functions. The first of the two is invisible but absolutely crucial. The face contains code that Sensor Watch executes regularly in the background. This code dynamically adjusts the time in minuscule increments to compensate for the effects of the current temperature on the crystal's frequency.

The second, visible function is a collection of screens where you can review and change various parameters that affect Nanosec's internal calculations. You essentially won't need to change any of these settings, but they are fun to review.

In each of the screens below, you can use LIGHT to increase the value and ALARM to decrease it. Where it makes sense, a long press means a larger change.

<img src="../images/nanosec-01-fc.png" width="120"/>
<img src="../images/next-mode-long.png" width="66"/>
<img src="../images/nanosec-02-t0.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/nanosec-03-2c.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/nanosec-04-3c.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/nanosec-05-pr.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/nanosec-06-cd.png" width="120"/>
<img src="../images/next-mode.png" width="66"/>
<img src="../images/nanosec-07-aa.png" width="120"/>

- FC: The static frequency correction value.
- T0: The crystal's center temperature, in °C. Nominally this is 25 °C for all crystals, but small variations are possible. A true center temperature improves the precision of dynamic frequency adjustments. However, in order to determine this value, a number of fine measurements are needed at controlled temperatures, which is beyond the reach of most Sensor Watch users.
- 2C: The quadratic coefficient in the formula that Nanosec uses to approximate the quartz crystal's temperature characteristics.
- 3C: The cubic coefficient in the formula that Nanosec uses to approximate the quartz crystal's temperature characteristics.
- PR: The correction profile (formula) used to model the crystal's temperature characteristics. You will most likely want to stick with P3, but see description of profiles below.
- CD: The cadence of time correction, i.e., the length of the interval (in minutes) at which Nanosec makes a minuscule adjustment to the time.
- AA: Aging compensation (ppm/year). The static frequency of crystals changes with age, but the exact value can only be determined empirically. If you notice that you keep adding 0.5 ppm each year to the static frequency correction to stay accurate, you can instead enter that value here.

### Nanosec correction profiles

This is what the various correction profiles do.

**P0**: Static hardware correction with 1ppm resolution. This has the least additional power draw because the correction is done entirely in the hardware.

**P1**: High-resolution (0.01ppm) static correction implemented in software. This is the profile you'd want to choose if your watch has no temperature sensor.

**P2**: High-resolution static correction, plus dynamic frequency correction for temperature changes. The dynamic correction uses the quadratic formula from the crystal's datasheet.

**P3**: Like P2, both static and dynamic correction, but using an empirically measured cubic formula.

**P4**: Custom settings for a specific crystal, using values that you can edit in the source code. You need to determine these values yourself; your crystal is unlikely to match what you find in the source code.