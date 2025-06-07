---
title: "Sensor Watch Accessory Board: Accelerometer"
linkTitle: "Sensor Watch Accessory Board: Accelerometer"
weight: 20
---
![Rendering: an L-shaped flex PCB labeled “Sensor Watch Accelerometer”](../images/accelerometer-sensor-board.png)

This sensor board shipped to all Sensor Watch Pro Crowd Supply backers. It is also available for separate purchase [at the Sensor Watch Pro page on Crowd Supply](https://www.crowdsupply.com/oddly-specific-objects/sensor-watch-pro).

Accelerometer
-------------

The accelerometer sensor board includes one active component: the [LIS2DW12 high-performance ultra-low-power 3-axis "femto" accelerometer](https://www.st.com/en/mems-and-sensors/lis2dw12.html) from STMicroelectronics. See the data sheet ([PDF link](https://www.st.com/resource/en/datasheet/lis2dw12.pdf)) for details, but in short, it has a configurable output rate from 1.6 Hz to 1600 Hz and two interrupts for a variety of conditions including tap detection, orientation change, and freefall, as well as a status output indicating whether the device is stationary or in motion. All of these interrupts come with configurable thresholds and durations.

While you can do a TON with this sensor, Second Movement configures it to be as low-power as possible: at boot, the accelerometer is set to its low-power (not high-performance) mode, and then it is configured for stationary/motion detection. It's configured to output this state on pin A4: if pin A4 reads high, the accelerometer is still; if A4 reads low, the accelerometer has recently experienced a high pass filtered acceleration event of >1g on one of its axes.

Then it's powered down, not to be activated unless a watch face requests it. A watch face can request the accelerometer via two functions: `movement_set_accelerometer_background_rate` and `movement_enable_tap_detection_if_available`. To help understand the power impact of thesr options:

* With the accelerometer powered down, as it is at boot, the accelerometer sensor board is consuming an additional 0.05 µA when compared to a board without the sensor installed.
* Calling `movement_set_accelerometer_background_rate` with a background rate of 1.6 Hz adds <1 µA of power consumption.
* Calling `movement_enable_tap_detection_if_available` adds about 150µA of power consumption. As such, tap detection should only be enabled briefly, and paired with a call to `movement_disable_tap_detection_if_available`.

Currently three watch faces make use of the accelerometer:

* The **Activity Logging** face will enable the accelerometer at a slow 1.6 Hz sampling rate at boot, and keep there indefinitely in the background. It will then log any consecutive minutes where pin A4 read low. In my experience, this is adequate to capture jogging workouts.
* The **Accelerometer Status** face displays the state of pin A4: active or still. If the accelerometer was on in the background, it will leave it at that sampling rate; if it was off, it will enable it at 1.6 Hz while the watch face is on screen. This watch face also allows you to change the threshold from 1 g to something else via a long press of the ALARM button.
* The **Countdown Timer** face will enable tap detection for three seconds when the face comes on screen. You can tap the watch to increment the number of minutes you want to count, and each tap will extend tap detection for another three seconds. Tap detection will be disabled after this timeout, or when the wearer presses the ALARM button to start the timer.

All of these functions return a boolean that indicates whether the operation was successful. If they return false, that means that an accelerometer board was not present; you may want to either update your UI to reflect this condition, or include logic to skip your watch face if the accelerometer is critical for your use case.

UART
----

In addition to the accelerometer, this sensor board also breaks out test points on the underside for two signals, A2 and A1, as well as power and ground. It will be fiddly, but you can solder fine enamel wires to these test points and run them out of the watch case, which will allow you to talk to the watch over UART. This could be useful if you are interested in streaming acceleration data out of the watch.
