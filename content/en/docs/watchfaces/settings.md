---
title: "Settings"
linkTitle: "Settings"
weight: 8
---
The watch faces in this section relate to watch configuration.

 * [Preferences](#preferences)
 * [Time Set](#time-set)

Preferences
-----------

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

The Time Set watch face allows you to set the time on Sensor Watch. Use the Light button to advance through the field you are setting, and the Alarm button to change the value in that field. The fields are, in order: Hour, Minute, Second, Year, Month, Day and Time Zone.

For features like World Clock and Sunrise/Sunset to work correctly, you must set the time to your local time, and the time zone to your local time zone. This allows Sensor Watch to correctly offset the time. This also means that when daylight savings time starts or ends, you must update both the time and the time zone on this screen.