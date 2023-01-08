---
title: "Designing a New Watch Face for Movement"
linkTitle: "Designing a New Watch Face for Movement"
weight: 50
---
In this document, we’re going to describe designing a single watch face for Movement, the community firmware for Sensor Watch. It's a simple watch face that simply blinks an LED, and provides some options for blink speed and color.

We’ll start by generating a header and an implementation for our blink watch face. First, open a terminal and navigate to the movement/template directory: `cd movement/template/`.

You can create a watch face in any of the major categories of watch face that Movement offers:

* `clock` faces tend to display the time, whether in a standard time system like a world clock or an alternative system like decimal time. The standard clock, Mars time and beat time all fit in this category.
* `complication` faces tend to display some non-time information, but don't generally require any data other than user input or the time. Sunrise, TOTP generation and dice rolling all fit into this category.
* `sensor` faces are a lot like complication faces, but tend to display information from sensors attached to the watch. Temperature display, accelerometer display and battery voltage fit in this category.
* `settings` faces are watch faces that involve configuring the watch.
* `demo` faces are faces that involve demonstrating or testing functionality.

Once you know the category of watch face you're building — blink is pretty clearly a complication — create the watch face files with the command `python3 watch_face.py complication blink` in a terminal window. That generates two files in the watch-faces/complication folder, called `blink_face.h` and `blink_face.c`. It also adds the watch face to both Movement's Makefile and its include files.

Take a look at `blink_face.h`. Watch faces in Movement are just plain old C, and we’ll implement our blink watch face in the four functions that script has generated for us:

* `blink_face_setup` is called when the watch boots, and when waking from deep sleep.
* `blink_face_activate` is called just before our watch face comes on screen.
* `blink_face_loop` is called every time the watch ticks, which is normally once a second, but watch faces can request something faster.
* And `blink_face_resign` is called just before our watch face goes off screen.

The script also generates a structure to hold the state of our watch face. We’ll want to add some stuff: a boolean to keep track of whether the LED should be actively blinking — an on/off switch, if you will — as well as the speed and the color. It looks something like this:

{{< highlight c >}}
typedef struct {
    bool active;
    bool fast;
    uint8_t color;
} blink_state_t;
{{< /highlight >}}

Next, we’ll look to our implementation file, `blink_face.c`, and implement those four functions. Our setup function is simple: when the watch boots, Movement will call this function with a spot for us to stash a pointer to our watch face state. We’ll just allocate some memory for that purpose, and zero it out:

{{< highlight c >}}
void blink_face_setup(movement_settings_t *settings, uint8_t watch_face_index, void ** context_ptr) {
    if (*context_ptr == NULL) {
        *context_ptr = malloc(sizeof(blink_state_t));
        memset(*context_ptr, 0, sizeof(blink_state_t));
    }
}
{{< /highlight >}}

Next, we’ll implement our activate function. When the wearer activates our watch face, we'll want to set up any initial state that makes sense when arriving at the watch face. The temperature log watch face, for example, moves to the most recently logged entry. For our blink face, we make sure to set the active property of our state to false so the light doesn't start blinking right away. (Note that we get a void pointer here, which we cast to our `blink_state_t` type. This "context" pointer may look confusing, but it’s just Movement giving us back the same pointer that we malloc‘ed in setup above.)

{{< highlight c >}}
void blink_face_activate(movement_settings_t *settings, void *context) {
    blink_state_t *state = (blink_state_t *)context;
    state->active = false;
}
{{< /highlight >}}

Before we declare our loop function, I’m going to add a little helper function to update the LCD. This just takes the state of our watch face, and translates it to letters on the LCD. This function formats a ten-character string that looks something like this: "BL F Green". The wearer can read that as "Blink face, fast blink, green LED".

{{< highlight c >}}
static void _blink_face_update_lcd(blink_state_t *state) {
    char buf[11];
    const char colors[][7] = {" red  ", " Green", " Yello"};
    sprintf(buf, "BL %c%s", state->fast ? 'F' : 'S', colors[state->color]);
    watch_display_string(buf, 0);
}
{{< /highlight >}}

The `watch_display_string` function then displays it in the ten positions available on the watch:

![Rendering: an L-shaped flex PCB labelled “Temperature+GPIO Sensor Board”](../images/blink-face.png)

Almost there! Next, we write our loop. This is where the action happens!

{{< highlight c >}}
bool blink_face_loop(movement_event_t event, movement_settings_t *settings, void *context) {
    blink_state_t *state = (blink_state_t *)context;

    switch (event.event_type) {
        // TODO: handle events!
    }

    return true;
}
{{< /highlight >}}

The core of this function is just a big switch statement that handles events. Movement abstracts away all of the button and timer interrupts, and instead gives our watch simple events that correspond to things like button presses or ticks. All we have to do is implement the cases. For example, we get an event when the watch face is first activated. We can use that to update the LCD for the first time:

{{< highlight c >}}
case EVENT_ACTIVATE:
    _blink_face_update_lcd(state);
    break;
{{< /highlight >}}

Next, let’s respond to a button press. When the wearer presses the Mode button, we’ll want to move to the next watch face:

{{< highlight c >}}
case EVENT_MODE_BUTTON_UP:
    movement_move_to_next_face();
    break;
{{< /highlight >}}

Simple enough! Now we need a way to change the color. We’ll assign that function to the Light button: when the wearer presses that button, assuming the LED isn’t already blinking, we’ll move to the next color and update the display:

{{< highlight c >}}
case EVENT_LIGHT_BUTTON_UP:
    if (!state->active) {
        state->color = (state->color + 1) % 3;
        _blink_face_update_lcd(state);
    }
    break;
{{< /highlight >}}

We’ll also need a way to start and stop the blinking. We’ll use the Alarm button for that. When the wearer presses that button, we want to do one of two things. If the blinking isn’t active, we set it to active, clear the display, and request a frequency to match the selected speed. If on the other hand the blinking is active, we’ll stop it and go back to displaying our state.

{{< highlight c >}}
case EVENT_ALARM_BUTTON_UP:
    if (!state->active) {
        state->active = true;
        watch_clear_display();
        movement_request_tick_frequency(state->fast ? 8 : 2);            
    } else {
        state->active = false;
        watch_set_led_off();
        _blink_face_update_lcd(state);
    }
    break;
{{< /highlight >}}

Of course, we also need to give the wearer a way to select the speed. But we’re out of buttons! Not to worry, there’s another event for that. Movement can detect a "long press" of a button, which is when the wearer holds the button for more than a half second. We’ll make a long press on the Alarm button change the speed (again, assuming the LED isn’t blinking):

{{< highlight c >}}
case EVENT_ALARM_LONG_PRESS:
    if (!state->active) {
        state->fast = !state->fast;
        _blink_face_update_lcd(state);
    }
    break;
{{< /highlight >}}

Finally, we need to blink the light! We’ll use the tick event for that. Movement issues this event every time the clock ticks. Normally that’s once a second, but watch faces can request a faster tick, like we did above when setting the blinking state to active. We’ll use this tick function to toggle the LED off on even numbered ticks, and on odd numbered ticks:

{{< highlight c >}}
case EVENT_TICK:
    if (state->active) {
        if (event.subsecond % 2 == 0) watch_set_led_off();
        else if (state->color == 0) watch_set_led_red();
        else if (state->color == 1) watch_set_led_green();
        else watch_set_led_yellow();
    }
    break;
{{< /highlight >}}

That’s it for our loop! There’s only one function left, and it’s a short one. Our resign function is responsible for any last-minute cleanup before relinquishing control to the next watch face. In our case, it’s possible the wearer might press "Mode" while the LED was on, so we need to make sure to turn it off here, just in case:

{{< highlight c >}}
void blink_face_resign(movement_settings_t *settings, void *context) {
    watch_set_led_off();
}
{{< /highlight >}}

With that, we’ve implemented a whole watch face in just a few dozen lines of code! All that’s left is opening up `movement_config.h` and adding it to the list of selected watch faces:

{{< highlight c >}}
const watch_face_t watch_faces[] = {
    simple_clock_face,
    blink_face, // that's us!
    voltage_face,
    preferences_face,
    set_time_face,
};
{{< /highlight >}}
