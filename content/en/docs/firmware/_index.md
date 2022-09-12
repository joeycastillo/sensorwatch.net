---
title: "Sensor Watch Firmware"
linkTitle: "Firmware Info"
weight: 10
---
While you can build any number of bare-metal applications for Sensor Watch, when we refer to the Sensor Watch firmware, we're really talking about _Movement_, the community firmware for Sensor Watch. You can read more about Movement [here](/docs/movement/); for now, the important thing to know is that it manages a series of _watch faces_ that you advance through using the _mode_ button. It's a very similar idiom to the classic Casio F-91W, which advances from `Clock -> Alarm -> Stopwatch -> Time Set`, and then wraps around to `Clock`.

Movement offers many more watch faces — some of which, like World Clock, you can include more than once! Still: you'd be pressing the Mode button for hours if we included them all, so instead, we only build a subset of the available faces into any given firmware. This means that you can [download an alternate firmware](/docs/firmware/prebuilt/) that includes the kind of functionality you want, or [build custom firmware](/docs/movement/building/) that includes just the watch faces you desire.
