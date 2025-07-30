---
title: "Second Movement: The Community Firmware for Sensor Watch"
linkTitle: "Second Movement: The Community Firmware for Sensor Watch"
weight: 25
---
_Second Movement_ is an application that manages the display of different screens of content on the watch. These screens are called _watch faces_. Watch faces can be passive displays of information like a clock or a calendar, or they can be fully interactive user interfaces like the Preferences face, which allows the user to customize Movement's behavior.

Second Movement handles the instantiation of your watch face and manages transitions between screens. It also provides a low-power sleep mode, triggered after a period of inactivity, to preserve the watch battery.

Several faces are provided that offer baseline functionality like a clock, a settings screen and an interface for setting the time. You can change and reorder the watch faces that Movement displays by editing movement_config.h, and you can write your own watch face using the guidance in this chapter.
