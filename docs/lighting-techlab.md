# Lighting Tech Lab

## ETC Element

**Software Version:** 2.3.9 (Final Release)

> This console hardware is now obsolete and will receive no further updates from ETC. However, it exists in a fully-working condition that allows it to be used in limited capacity as a teaching tool as the control surface and user interface remains similar to later models.

[Product Info](https://www.etcconnect.com/Products/Legacy/Console/Eos-Family/Element/Features.aspx)

[Online Manual](https://www.etcconnect.com/WorkArea/DownloadAsset.aspx?id=10737500524)

## Patching Demo

### Fixture Configuration

The following demonstration will use a generic 7-channel RGB LED light bar. We will only utilize the Red, Green, and Blue channels of this device to make those lights available to the ETC console.

**Device Configuration:**

1. Press up/down to get to the “d” prefix options.
2. Use inc/dec to set to “d010”

**What does this do?**

* The “d” prefix is the correct one for this particular device which gives us DMX control.
* We set an address of “010” as the starting point for the fixture’s DMX channels.

> This fixture provides built-in effects but we will not be using those program modes through the ETC console. By patching through DMX we will have control over the individual RGB LEDs and will use the console to set levels.

### EOS Element Configuration

1. Ceate a new show file for your work, saving with a custom name to track your progress.
2. Locate and press the `[Patch]` key on the console.
3. Enter the text `1 thru 3 @ 10` and press `[Enter]`

**What does this do?**

* Since we selected “010” as the address of the fixture, this becomes the starting point for any assignment to channels.
* The fixture offers 3 direct controls for the Red, Green, and Blue LED lights, each as a distinct address where Red = 10, Green = 11, and Blue=12.
* The `1 thru3 ` represents the channels on the ETC console where we want those 3 colors to be accessible.
* The `@ 10` tells the console to begin the patching of the 3 channels to addresses in sequential order:
	* 1=10
	* 2=11
	* 3=12

**Adding Labels (Optional):**

To remember what each channel/address combination represetnts you can add a Label/Note to the patch assignment while in the Patch screen.

1. `[Patch]`
2. `1 [Label] Red [Enter]`
3. `2 [Label] Green [Enter]`
4. `3 [Label] Blue [Enter]`

> Note: If you need to clear everything previously patched on this console in order to start with a clean slate, use `[Patch] 1 thru 3 [Delete] [Enter]`.
> NEVER perform this action on a live or established ETC console without sufficient backups of show files!

### Testing the Lights

1. Locate and press the `[Live]` key on the console.
2. Set the Grand Master above zero (0) or to full so you can see any effects.
3. Use the sliders for channels 1-3 to adjust the Red, Green, and Blue lights of the fixture.

### Next Steps

At this point you should have a working fixture which is controlled through the ETC console. Begin working on show cues to demonstrate fade-in's, blackouts, color changes, and other transitions. Try adding additional DMX fixtures and patching to channels to expand your setup!