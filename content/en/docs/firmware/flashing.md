---
title: "Flashing Firmware onto Sensor Watch"
linkTitle: "Flashing Firmware onto Sensor Watch"
weight: 15
---
The small spade at the top of Sensor Watch is designed to plug directly into a USB Micro B cable. This allows you to flash new firmware directly onto the device via the built-in UF2 bootloader.

To accomplish this, disassemble your watch completely, and plug the Sensor Watch board into a USB Micro B cable plugged into your computer. Double tap the tiny Reset button on the back of the board; the LED should begin to pulse red (or blue, for Special Edition boards). You should see a disk drive called "WATCHBOOT" appear on your computer.

Drag a UF2 file with the firmware you want to use onto the WATCHBOOT drive. You can find some [prebuilt firmware images](/docs/firmware/prebuilt/) right here on the Sensor Watch website, or you can [build your own firmware](/docs/movement/building/) with just the watch faces you want to wear.

After you drag the file over to WATCHBOOT, the LED should pulse intensely for a few seconds, and then turn off. This signals that the firmware has uploaded successfully; you can now reassemble the watch and wear the new firmware on your wrist.

**NOTE:** As a failsafe (in case the watch inadvertently enters bootloader mode while being worn), the bootloader is programmed to exit after 60 seconds of inactivity. This means that once you enter bootloader mode (red LED pulsing), you have one minute to copy over your firmware, or the watch will exit bootloader mode, and you will have to double-tap reset again.
