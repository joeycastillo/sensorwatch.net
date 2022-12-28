---
title: "Building Sensor Watch Firmware"
linkTitle: "Building Sensor Watch Firmware"
weight: 30
---

Install the cross-compiling toolchain on Linux
----------------------------------------------

* Ubuntu: `apt install gcc-arm-none-eabi`

* Archlinux: `pacman -S arm-none-eabi-gcc`

Other Linux:

* Download the [GNU ARM Embedded Toolchain for 64-bit Linux](https://developer.arm.com/-/media/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2?rev=78196d3461ba4c9089a67b5f33edf82a&hash=5631ACEF1F8F237389F14B41566964EC)
* Extract it: `tar xjf gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2`
* Add it to your PATH: `export PATH="$PATH:/path/to/extracted/gcc-arm-none-eabi-10.3-2021.10/bin"`

Note: if you want, you can add the above PATH export to your shell's startup script to make it persist between shell invocations

Install the cross-compiling toolchain on MacOS
----------------------------------------------

* Download the [GNU ARM Embedded Toolchain for 64-bit MacOS](https://developer.arm.com/-/media/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-mac.pkg?rev=b382d51ec8d34c3fa421cf57ce97f146&hash=86689FEB39DA7A381FF78A2E70F7ABCE)
* Double-click the installer and follow the prompts to install the toolchain
* Add the toolchain to your PATH: `export PATH="$PATH:/Applications/ARM/bin"`

Note: if you want, you can add the above PATH export to your shell's startup script to make it persist between shell invocations

Compile firmware
----------------

* From within the [repo](https://github.com/joeycastillo/Sensor-Watch):
* `cd movement/make`
* `make`

The built firmware will be at `build/watch.uf2`. You can now [flash](/docs/firmware/flashing) this firmware to your watch.

"I just want to pick my own set of watchfaces"
----------------------------------------------

The list of included watchfaces can be found in the `watch_faces` array in `movement/movement_config.h`. Simply add, remove, and/or rearrange faces in this list to your liking and re-compile/re-flash your firmware.
