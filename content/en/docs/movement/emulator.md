---
title: "Building Firmware for the Sensor Watch Emulator"
linkTitle: "Building Firmware for the Sensor Watch Emulator"
weight: 40
---

Install the Emscriptem (WASM) cross-compiling toolchain on Linux
----------------------------------------------------------------

* Debian/Ubuntu: `apt install emscripten`

Compile firmware
----------------

* From within the [repo](https://github.com/joeycastillo/Sensor-Watch):
* edit make_alternate_fw.sh to select which build(s) you want
* `cd movement/make`
* `./make_alternate_fw.sh`

The built firmware will be at `movement/make/firmware/simulate/standard`. You can now run this firmware in your browser with `emrun`:

* `cd movement/make/firmware/simulate/standard`
* `emrun index.html`
