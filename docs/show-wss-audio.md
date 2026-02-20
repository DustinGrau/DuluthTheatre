# West Side Story - Audio Setup

**Show Date:** February 2026

## Mixer Features

For many technical reasons we used the Yamaha TF-5 normally housed in the tech booth for audio mixing in this show. The analog board would not be able to keep up with the significant changes between scenes and we wanted to use more advanced features as found on a modern mixing console. More details about scenes can be found in the show's [scene notes page](show-wss-scenes.md).

### Recording Output Mix

In order to provide a clean signal to record the show (as needed for the Shuler adjudication performance) we must have a dedicated signal using both left and right stereo signals, downmixed to mono. This can be easily accomplished with the TF-5 using a Matrix output.

1. Select the GROUPS button beside INPUT 1 and INPUT 2 buttons on the console (above the Master fader).
2. Select `Matrix 1` from the 4 matrix outputs.
3. Select the SEND FROM button on `Matrix 1`.
    * Turn off all channels except `Stereo L` and `Stereo R`.
    * Set the volume for both Stereo outputs to unity (or -2dB).
    * Make sure the matrix is configured as mono (no stereo paired).
    * Make sure the matrix is post-fader (default when from master).
4. Assign `Matrix 2` to an unused OMNI output for recording use (13).
5. Repeat steps 2-4 to create a `Matrix 2`.
6. Assign `Matrix 1` to an unused OMNI output for lobby output (14).

### Custom Fader Bank

Normally, the TF-5 would allow you to mix channels 1-32 plus the Main mix while on the INPUT 1 view. But with using DCAs we need a more comprehensive console surface. The TF-5 allows you to create your own custom fader bank, which can consist of any channels and DCA groups in a single view across the mixer. For this show it was useful to show all available mic'd actors as well as the DCAs they may be assigned into, and the fader for the music source (laptop).

* Press the INPUT 2 and OUTPUT buttons
* Select all desired channels and DCAs

### Aux Busses

We commonly utilize 2 AUX busses for monitors. AUX 1 is the stage monitors while typically AUX 3 is the wing monitors. For this show we needed to switch the stagebox backstage to be UNIT 2 so our output for the wing monitors was moved to AUX 9/10. Bottom line: same idea, just slightly different output. For sake of clarity we can just think of the AUX busses as just STAGE MONITORS and WING MONITORS.

#### AUX 1 - Stage Monitors

* Set the MAIN level around 0dB (Unity) for this AUX output to synchronize with the house at 0dB.
* Set ONLY the channel with music (laptop) to output to this AUX as Post-Fader (turn off PRE).
* Set the music channel 32 to +10dB so that it stays ABOVE the house level's output for music.
* Volume to this AUX output will follow the fader, keeping it in sync with loudness in the house.

| AUX 1  |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 |  32 | M |
|--------|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|-----|---|
| VOLUME |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    | +10 | 0 |

#### AUX 7 - Balcony Monitor

* Set the MAIN level around 0dB (Unity) for this AUX output to keep it as "hot" as possible.
* Keep the channel with music (laptop) to output to this AUX as PRE-fader to allow direct control.
* Set the music channel 32 to around -20dB so that it stays constant and BELOW the stage monitors.
* This should ONLY be used with the **Balcony Scene** to avoid music bleed during other music fades!
* The balcony monitor will be patched to OUTPUT 1 on the stagebox (currently AUX 7 as UNIT 2).

| AUX 7  |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 |  32 | M |
|--------|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|-----|---|
| VOLUME |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    | -20 | 0 |

#### AUX 9/10 - Wing Monitors

* Set the MAIN level around -10dB for this AUX output so actors in the wings can still hear the stage.
* Set the channel with music (laptop) to output to this AUX as Post-Fader (turn off PRE).
* Set all mic'd actor channels to this AUX as Post-Fader (turn off PRE).
* Set the music channel to 0dB so that it has no +/- adjustments, and actors get full volume.
* Set all actor mics to -5dB to keep the music channel more pronounced.
* Add an EQ to the mix to reduce lower frequencies and increase higher frequencies (emphasizes voices).
* Volume to this AUX output will follow all faders, keeping the overall mix intact.
* The wing monitors will be patched to OUTPUT 3 on the stagebox (currently AUX 9 as UNIT 2).

| AUX 9  |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 32 | M |
|--------|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|---|
| VOLUME | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 | -5 |    |    |    | -5 | -5 |    |    | -5 |    |    |    |    |    |    |    |  0 | 0 |

## Channel Assignments

This is the most critical piece of planning audio for a show as this is the "source of truth" for the actors to know which mic is theirs, and keeps consistency which is absolutely necessary for scenes. In this case we needed all available wireless mic receivers to be available, even though we could not provide a headset mic to every named character. The choice of wireless mic was also carefuly chosen to maximize quality/reliability for pricipal actors, followed by supporting actors, and lastly ensemble members.

**Key:**

* WL# = QLXD4 (1-10)
	* Highest quality mic system, operates on a distinct frequency band.
	* Reserved primarily for heavy dialog/singing roles.
* WMIC# = SLX4 (1-10, 11-16, 17)
	* Mid-quality mic system, with potential overlap from outside radio sources.
	* Mics 11-16 belong to a mobile "cart" and use distinct group/channel bands.
	* Mics 1-10 & 17 are part of the house system and use auto-assigned channels.
	* TIP: Turn on all available receivers/transmitters before using auto-assignment.
* BLX4R = Handheld Wireless
	* Standard handheld mic for special roles or purposes (eg. pre-show introductions).
* Op1 - Optional Tier 1
	* Character with a significant role, but can only be mic'd as hardware is available.
* Op2 - Optional Tier 2, Mic'd if Available
	* Character with a less-significant role, but can only be mic'd as hardware is available.

|   CHANNEL    |   MIC                 |   CHARACTER/ACTOR           |  ROLE       |
|--------------|-----------------------|-----------------------------|-------------|
|   1          |   WL1  [Crate]        |   Maria - Emma              | Principal   |
|   2          |   WL2  [Crate]        |   Tony - K’von              | Principal   |
|   3          |   WL3  [Crate]        |   Riff - Grant              | Principal   |
|   4          |   WL4  [Crate]        |   Bernardo - Kevin          | Principal   |
|   5          |   WL5  [Crate]        |   Anita - Roan              | Principal   |
|   6          |   WL6  [Crate]        |   Action - Julian           | Jets        |
|   7          |   WL7  [Crate]        |   Diesel - Landen           | Jets        |
|   8          |   WL8  [Crate]        |   Baby John - Lyle          | Jets        |
|   9          |   WL9  [Crate]        |   Chino - Nathan            | Sharks      |
|   10         |   WL10 [Crate]        |   Doc - Idris               | Adults      |
|   11         |   WMIC11 [Crate]      |   Ofc. Krupke - Andrik      | Adults      |
|   12         |   WMIC12 [Crate]      |   Lt. Schrank - Razmilla    | Adults      |
|   13         |   WMIC13 [Crate]      |   Anybodys - Emi            | Jets        |
|   14         |   WMIC14 [Crate]      |   Jet Girl - Liz            | Jets        |
|   15         |   WMIC15 [Crate]      |   Francisca - Sally         | Sharks      |
|   16         |   WMIC16 [Crate]      |   Consuela - Naomi          | Sharks      |
|   17         |   WMIC2  [Booth]      |   *Graziella - Maddie*      | Sharks      |
|   18         |   WMIC3  [Booth]      |   *Big Deal - Elijah [Op1]* | Jets        |
|   19         |   WMIC4  [Booth]      |   *Snowboy - Jaden [Op1]*   | Jets        |
|   20         |   WMIC5  [Booth]      |   A-Rab - Dylan [Op2]       | Jets        |
|   21         |   WMIC6  [Booth]      |   Rosalia - Evelyn [Op1]    | Sharks      |
|   22         |   WMIC7  [Booth]      |   *Indio - Tyreek [Op2]*    | Sharks      |
|   23         |   WMIC8  [Booth]      |   *Pepe - Aristides [Op2]*  | Sharks      |
|   24         |   BLX4R  [Booth]      |   Glad Hand                 | Adults      |
|   25         |   Stage Overhead (L)  |   Ensemble/Atmosphere       | Stage       |
|   26         |   Stage Overhead (C)  |   Ensemble/Atmosphere       | Stage       |
|   27         |   Stage Overhead (R)  |   Ensemble/Atmosphere       | Stage       |
|   28         |   -OPEN-              |                             |             |
|   29         |   -OPEN-              |                             |             |
|   30         |   -OPEN-              |                             |             |
|   31         |   -OPEN-              |                             |             |
|   32         |   Laptop (Music)      |                             |             |

### Channel Volume

When using TheatreMix, any channel which is NOT in a scene will be automatically muted. But when unmuted we need a standard volume for each actor so that when mixed via DCA we are simply applying an adjustment to that level. In order to make the DCA become the "source of truth" we need EVERY USED channel set to 0dB (unity) so there is no +/- adjustment to the original actor's level.

For mic check, you can simply turn on the channel manually, set the fader to 0dB, and adjust the gain to achieve the proper volume for the actor. With the channel at unity this means the actor's most powerful voice should be close to but not above the center GREEN bar on the gain display. Once an actor is at their desired gain and unity, push the volume to +10dB to test for feedback--if you get a ringing or hum then back off of the gain slightly. This will give you a usable range above the norm to boost the actor when needed, while avoiding the point where they may get feedback.

| MAIN   |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 32 | M |
|--------|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|----|---|
| VOLUME |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |    |    |    |  0 |  0 |    |    |  0 |    |    |    |    |    |    |    |    | 0 |