# Audio Tuning

## Theatre Audio Settings

High Pass Filter
Men: 80-100Hz
Women: 100-150Hz

1-Knob EQ - Vocal Mode
Automatic EQ w/ HPF for vocal ranges (40-100)

* [https://www.youtube.com/watch?v=VXWoM0M9XKg](https://www.youtube.com/watch?v=VXWoM0M9XKg)
* [https://www.youtube.com/watch?v=SSSA7HPvC1g](https://www.youtube.com/watch?v=SSSA7HPvC1g)

1-Knob EQ - Intensity Mode
Affects amount of effect for any set EQ points

1-Knob Compressor
Keep subtle to remove peaks and boost lows (~50, 2.0:1-2.5:1)
[https://www.youtube.com/watch?v=6KDhgoDUyAw](https://www.youtube.com/watch?v=6KDhgoDUyAw)


## Shure SLX1 Wireless Mics

Countryman Headsets

[TA4F Connector](https://service.shure.com/s/article/pin-out-for-shure-bodypack-transmitters-and-preamps-ta4m-ta4f?language=en_US) - Mini XLR 4 Pin

	Pin 1: Shield
	Pin 2: Bias (+5Vdc)
	Pin 3: Audio
	Pin 4: Bias return - 20 k Ohm resistor to ground or equivalent active bias management circuit
	(Jumpered to pin 3 when used with most condenser microphones)

![](ta4f.jpg)

The pictorial shows the pin layout of a TA4F connector, as viewed from the wiring side. If you use a bright light and look at the female connector (TA4F) used for the cable, you will see numbers next to each hole. The TA4F cable end connector can be purchased as Shure Part #WA330.  ### Applications:
 Condenser Microphones - Shure WH30, PG30, WL18x, WL50, WL51, WL93, etc. 
* Connect audio lead (black) to pins 3 and 4 * Connect bias lead (red) to pin 2 * Connect shield to pin 1 and connector body (use cable clamp insert piece as the connector body terminal)

[Replacement cable for countryman mics](https://www.sweetwater.com/store/detail/E6CableT1SL--countryman-isomax-e6-replacement-cable-for-shure-tan-1mm-cable) (threaded mic end, TA4F connector to transmitter)

Pyle-Pro mic headset as a low-cost alternative for the countryman headsets

* [https://a.co/d/j9ar9OH](https://a.co/d/j9ar9OH)
* [https://a.co/d/4YVe7Mj](https://a.co/d/4YVe7Mj)

Look at [Microphone Madness](https://www.microphonemadness.com/mm-dual-ear-psm-pro-series-dual-earset-microphone.html)

## Lav Tester / Preamp

* [http://www.scotthelmke.com/lav-amp.html](http://www.scotthelmke.com/lav-amp.html)
* [http://www.scotthelmke.com/Lav-tester-shure.jpg](http://www.scotthelmke.com/Lav-tester-shure.jpg)
* [https://www.digikey.com/en/products/detail/texas-instruments/TLE2426CLP/276234](https://www.digikey.com/en/products/detail/texas-instruments/TLE2426CLP/276234)
* [https://www.digikey.com/en/products/detail/texas-instruments/TL072CP/277421](https://www.digikey.com/en/products/detail/texas-instruments/TL072CP/277421)

![](lav-tester-shure.jpg)


## Room EQ Wizard

**Preferences**

* Output: Headphones
* Input: Umik-1 USB Mic
* Sweep Level: -12dBFS (for test tones)

**Process**

1. Set up reference mic at 90-degrees at ear level for listening space.
2. Open the SPL Meter, Generator (to Noise tab), and Levels Meter.
3. Turn down speakers first, connect audio output to system.
4. Set generator to white (random) noise at -12dBFS, press Play.
5. Slowly raise the speaker levels until reaches at least 76dB(A) on the SPL Meter (and not clipping on Levels Meter).
6. Close the Generator, and SPL/Levels Meter windows.
7. Click on the Measure button at top left to open Measurements Window.
    * Type: SPL
    * Method: Sweep
    * Settings: 512k Length / 2 Iterations
    * Range: 15-20,000Hz
    * Level: -12dBFS
    * Output: Line Out (should measure L, R, and both together)
    * Press the Start button to begin sweeps and measurement
8. Observe the output in the respective displays
    1. SPL (Graph -> 1/6 Smoothing) - Shows which frequencies are over/under-pronounced at listening position
        * Can optionally check the Phase response by checking box below the graph
        * Ideally should have +/-5dB of difference between frequency responses
    2. Waterfall - Decay times of sound waves (shows those that “linger” or have a “null” in the room)
        * Emphasize select ranges, such as 20-300Hz:
            * Limits: 20Hz (left) - 300Hz (right)
            * Controls: 30ms (window) 500ms (time range)
    3. Spectrogram - Shows the waterfall view from above
        * Colors: SPL for frequencies
        * Axis: decay times over frequency

