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

Clone the [repo](https://github.com/joeycastillo/second-movement), and install submodules. Then from a terminal, run  `emmake make`. The built firmware will be output to the `build-sim` directory. 

You can now run this firmware in your browser by serving it over HTTP: `python3 -m http.server -d build-sim`. You'll access it at [http://localhost:8000/firmware.html](http://localhost:8000/firmware.html)
