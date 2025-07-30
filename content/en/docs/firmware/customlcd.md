---
title: "Building Firmware for the Custom LCD"
linkTitle: "Custom LCD"
---
**TL;DR: If you are upgrading an existing Sensor Watch or Sensor Watch Lite board, you will need to re-flash your board with new firmware to take advantage of the new display.** [Firmware images are linked below.](#flashing-pre-built-firmware)

All variants of Sensor Watch — Sensor Watch Pro, Sensor Watch Lite and both the green and blue versions of the original Sensor Watch board — have the ability to drive either the classic Casio LCD, or the new custom LCD designed by Oddly Specific Objects and available from Crowd Supply, but you need a firmware image targeted to your display. Your two options are to download a pre-built firmware image, or to build your own custom firmware with support for the custom LCD. 

Boards ordered on Crowd Supply ship with a special firmware image that can support both displays, but we still highly recommend replacing that firmware with a version targeted to your chosen display.

### Flashing Pre-Built Firmware

For the sake of convenience, a pre-built firmware image for the standard Second Movement firmware is provided here. Select the firmware image that matches your board variant and your choice of LCD:

* Sensor Watch Lite
    1. [Original Casio display](/docs/firmware/download/standard_red_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_red_custom.uf2)
* Sensor Watch Pro
    1. [Original Casio display](/docs/firmware/download/standard_pro_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_pro_custom.uf2)
* Sensor Watch Classic (green boards)
    1. [Original Casio display](/docs/firmware/download/standard_green_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_green_custom.uf2)
* Limited Edition Sensor Watch (blue boards)
    1. [Original Casio display](/docs/firmware/download/standard_blue_classic.uf2)
    1. [New Custom LCD](/docs/firmware/download/standard_blue_custom.uf2)

More custom firmware images are available on the [Prebuilt Alternative Firmware](/docs/firmware/prebuilt/) page.

### Building Custom Firmware

If you want to use watch faces not available in the prebuilt images, uou can also [clone the Second Movement repository](https://github.com/joeycastillo/second-movement) and 
[build your own firmware image](/docs/movement/building/). Make sure to add `DISPLAY=classic` or `DISPLAY=custom` as a flag to make; this will ensure that the built firmware image targets the display you have installed.

### Second Movement Builder

We are working on a web-based GUI for point-and-click generation of Sensor Watch firmware images.

Watch this space!
