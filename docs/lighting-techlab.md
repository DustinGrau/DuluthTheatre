# Lighting Tech Lab

## ETC Element

This is the former lighting console used in the DHS theatre up until 2023 when the lighting system was upgraded to use LED fixtures and a new Ion XE 20 console. The old console remains functional and represents a limited but consistent interface for ETC products both in terms of button layout and functions, as well as the ETC software itself. Learning the basics on this equipment will prepare you for understanding an industry-standard lighting system.

[Product Info](https://www.etcconnect.com/Products/Legacy/Console/Eos-Family/Element/Features.aspx)

[Online Manual](https://www.etcconnect.com/WorkArea/DownloadAsset.aspx?id=10737500524)

> This console hardware is now obsolete and will receive no further updates from ETC. However, it exists in a fully-working condition that allows it to be used in limited capacity as a teaching tool as the control surface and user interface remains similar to later models. For more information about the hardware used in this lab see the [tech specs document](lighting-techlab-specs.md).

## Sample Fixture Configuration

The following demonstration will use a generic 7-channel RGB LED light bar. We will only utilize the Red, Green, and Blue channels of this device to make those lights available to the ETC console.

**Device Configuration:**

1. Press up/down to get to the “d” prefix options.
2. Use inc/dec to set to “d010”

**What does this do?**

* The “d” prefix is the correct one for this particular device which gives us DMX control.
* We set an address of “010” as the starting point for the fixture’s DMX channels.

> This fixture provides built-in effects but we will not be using those program modes through the ETC console. By patching through DMX we will have control over the individual RGB LEDs and will use the console to set levels.

## Patching Demo - Raw DMX

Within the ETC console you can perform manual patching of a fixture, which is essentially treating each DMX channel as an individual control (such as separate dimmers for red, green, and blue), or you can apply a fixture profile, which allows the console to treat a group of DMX channels as a single light with multiple controllable attributes such as color and intensity. Before we run we need to walk, so let’s look at the concept of manual patching first.

### EOS Element Configuration

1. Ceate a new show file for your work, saving with a custom name to track your progress.
2. Locate and press the `[Patch]` key on the console.
3. If the prompt says "Patch Address" press the `[Format]` key to switch to "Patch Channel"
4. Enter the text `1 thru 3 @ 10` and press `[Enter]`

**What does this do?**

* Since we selected “010” as the address of the fixture, this becomes the starting point for any assignment to channels.
* The fixture offers 3 direct controls for the Red, Green, and Blue LED lights, each as a distinct address where Red = 10, Green = 11, and Blue=12.
* The `1 thru3 ` represents the channels on the ETC console where we want those 3 colors to be accessible.
* The `@ 10` tells the console to begin the patching of the 3 channels to addresses in sequential order:
	* Channel 1 = DMX 10
	* Channel 2 = DMX 11
	* Channel 3 = DMX 12

**Adding Labels (Optional):**

To remember what each channel/address combination represetnts you can add a Label/Note to the patch assignment while in the Patch screen.

1. Press `[Patch]` and make sure you are in "Patch Channel" format.
2. `1 [Label] Red [Enter]`
3. `2 [Label] Green [Enter]`
4. `3 [Label] Blue [Enter]`

> Note: If you need to clear everything previously patched on this console in order to start with a clean slate, use `[Patch] 1 thru 3 [Delete] [Enter]`.
> NEVER perform this action on a live or established ETC console without sufficient backups of show files!

### Testing the Lights

1. Locate and press the `[Live]` key on the console.
2. Set the Grand Master above zero (0) or to full so you can see any effects.
3. Use the sliders for channels 1-3 to adjust the Red, Green, and Blue lights of the fixture.

## Patching Demo - Fixture Profile

Instead of manually patching each DMX channel, the ETC console can use a fixture profile to understand how a light behaves. This allows the console to treat multiple DMX channels as a single fixture with defined attributes such as color and intensity.

Before proceeding with this step, be sure to complete the fixture configuration step as outlined above to give your fixture a unique DMX starting address. The following steps will continue to assume an address of `10` was set for the same RGB LED light bar.

> Be sure to start a new show file for this exercise to avoid conflicts with prior patching. For any DMX address you can only patch it once to a channel or fixture.

### EOS Element Configuration

In manual patching, you control each channel individually. With a fixture profile, the console groups those channels together and provides higher-level control. For this demonstration, we will use a generic RGB fixture profile rather than creating one from scratch.

1. Locate and press the `[Patch]` key on the console.
2. If the prompt says "Patch Address" press the `[Format]` key to switch to "Patch Channel"
3. Enter a channel number for the fixture: `1 [Enter]`
4. Click on the `Type` box on the right-hand side of the screen
5. Click on the `Search` button and look for "Generic > LED RGB > LED RGB 8b [3]"
6. Assign the starting DMX address: `@ 10 [Enter]`

**What does this do?**

The console now understands that this fixture is an LED RGB device which uses three [3] DMX channels for color control, with 8-bit (8b) values 0-255 for brightness. Channel 1 now represents the entire fixture, not just a single DMX address. You will now see that this type appears to immediately take 3 addresses because the console automatically maps:

* Red = DMX 10
* Green = DMX 11
* Blue = DMX 12

Using the Fixture

1. `[Live]`
2. Show the new light at full intensity with `1 @ Full [Enter]`
3. Alternatively, adjust intensity using the fader
4. Use available color controls (if displayed) to select colors instead of defaulting to all @ full

**Benefits of Using a Fixture Profile**

* Simplifies control by grouping related DMX channels
* Allows direct color selection instead of manual RGB mixing
* Enables use of:
  * Color palettes
  * Effects
  * More advanced console features

**Important Note**

You cannot patch both manual channels and a fixture profile to the same DMX addresses. Choose one method:

* Manual patching for learning fundamentals
* Fixture profiles for practical operation
* Optional: Creating a Custom Fixture Profile

> For advanced use, you can define your own fixture profile using the console’s fixture editor. This allows you to map DMX channels exactly as defined by the device, including additional controls such as strobe or program modes.

For this exercise, the generic RGB fixture provides all required functionality.

## Next Steps

At this point you should have a working fixture which is controlled through the ETC console. Now you may begin working on show cues to demonstrate fade-in's, blackouts, color changes, and other transitions. Learn how to create a magic sheet and light plot, and manage show information with 2 displays and keyboard shortcuts. Try adding additional DMX fixtures and patching to channels to expand your setup!

## Universes

Up until now we have not discussed the concept of a Universe in DMX, which is a collection of up to 512 address spaces.

Patching so far has used a single number for both the fixture and the ETC console. Technically, we have been working within Universe 1, using addresses such as 1/10 through 1/12, where 1/ designates the Universe and the number represents the DMX address within that Universe.

In larger systems, multiple Universes are used to expand the number of controllable devices. These may be organized by physical areas such as Front of House (FOH), stage electrics (1st electric, 2nd electric, etc.), or other logical groupings.

While the ETC Element lighting console supports only a single Universe, larger consoles such as the ETC Ion Xe 20 used in the theatre space supports multiple Universes.