# West Side Story - Audio Setup

**Show Date:** February 2026

## Mixer Features

### Recording Mix

As the music uses some panning audio, we need a stereo-to-mono mix of the final mix from the TF-5 which can be output to the iMac for recording of the performance. This is useful for the Shuler performance which requires a recording of the show. It also allows a single feed to the lobby speakers using the same mix. To do this we can use Matrix output.

1. Select the GROUPS button beside INPUT 1 and INPUT 2 buttons on the console (above the Master fader).
2. Select `Matrix 1` from the 4 matrix outputs.
3. Select the SEND FROM button on `Matrix 1`.
    * Turn off all channels except `Stereo L` and `Stereo R`.
    * Set the volume for both Stereo outputs to unity (or -2dB).
    * Make sure the matrix is configured as mono (no stereo paired).
    * Make sure the matrix is post-fader (default when from master).
4. Assign `Matrix 1` to an unused OMNI output for lobby output (14).
5. Assign `Matrix 1` to an unused OMNI output for recording use (13).

### Dugan Bypass

This show made use of the Dugan Automixer on channels 1-8 which will help with dialog from actors assigned to those channels. However, for songs where multiple actors in that group may contribute we want them all to be heard--this means being able to quickly bypass the Dugan Automixer for a brief period.

* Assign a user-defined key to turn Dugan on/off
    * Disabling is encouraged for large musical numbers
    * Person Setting (top-right icon) > User Defined Controls
    * Keys > A > Function: Automixer, Parameter 1: Bypass, Parameter 2: Group A
* No case for A/B grouping for this show (use Group A only)
* Start with default weighting and adjust if needed

### DCA Groups

Groupings of mics can be accomplished with DCA groups. These groups can be adjusted as a whole using the fader or even muted entirely by turning off the group.

Some notes when using DCA groups:

* Do not assign any single fader to more than 1 DCA group. This can lead to unexpected volume levels if the individual channel and the DCA groups which use it are set to different levels. Also, muting of any DCA group with that channel will mute it entirely, even if the channel or another DCA group is active.
* Individual channels and DCA groups can both be given an EQ or Compressor. The benefit of using compression on a group is to ensure that all members of the DCA group are kept within range, while compression on an individual channel ensures that person in isolation is kept within range for their performance.
* When in the Groups view, the individual members are displayed to the left when a DCA group is selected. This allows access to both the group volume as a whole as well as the mic'd actors, avoiding the need for "chasing faders".
* , allowing time to turn off channels

To access DCA groups and assign channels:

* Press both INPUT1 + INPUT2 to access Groups
* Select a group channel and press "DCA Assign" on the menu screen
* Touch a channel name to select/deselect for the DCA group

### Create a Custom Fader Bank

The TF-5 allows you to create your own custom fader bank, which can consist of any channels and DCA groups in a single view across the mixer.

* Press the INPUT 2 and OUTPUT buttons
* Select all desired channels and DCAs

### Aux Busses

* Potentially change AUX 1 to use Post-Fader through the BUS SETUP screen
    * This will ensure that music to the stage monitors is relative to the house
    * Setup (gear icon) > Bus Setup > AUX 1/2, deselect  the Pre Fader button
    * Ensure that AUX 1/2 and AUX 3/4 and set as Mono x2

## Channel Assignments

* WL# = QLXD4 (1-10)
* WMIC# = SLX4 (1-10, 11-16, 17)

|   CHANNEL    |   MIC                 |   CHARACTER/ACTOR         |  GROUPING   |
|--------------|-----------------------|---------------------------|-------------|
|   1 (Dugan)  |   WL1  [Crate]        |   Maria - Emma            | Principals  |
|   2 (Dugan)  |   WL2  [Crate]        |   Tony - K’von            | Principals  |
|   3 (Dugan)  |   WL3  [Crate]        |   Riff - Grant            | Principals  |
|   4 (Dugan)  |   WL4  [Crate]        |   Bernardo - Kevin        | Principals  |
|   5 (Dugan)  |   WL5  [Crate]        |   Anita - Roan            | Principals  |
|   6 (Dugan)  |   WL6  [Crate]        |   Action - Julian         | Jets        |
|   7 (Dugan)  |   WL7  [Crate]        |   Diesel - Landen         | Jets        |
|   8 (Dugan)  |   WL8  [Crate]        |   Baby John - Lyle        | Jets        |
|   9          |   WL9  [Crate]        |   Chino - Nathan          | Sharks      |
|   10         |   WL10 [Crate]        |   Doc - Idris             | Adults      |
|   11         |   WMIC11 [Crate]      |   Ofc. Krupke - Andrik    | Adults      |
|   12         |   WMIC12 [Crate]      |   Lt. Schrank - Razmilla  | Adults      |
|   13         |   WMIC13 [Crate]      |   Anybodys - Emi          | Jets        |
|   14         |   WMIC14 [Crate]      |   Velma - Lilian          | Jets        |
|   15         |   WMIC15 [Crate]      |   Francisca - Sally       | Sharks      |
|   16         |   WMIC16 [Crate]      |   Consuela - Naomi        | Sharks      |
|   17         |   WMIC2  [Booth]      |   Graziella - Maddie      | Sharks      |
|   18         |   WMIC3  [Booth]      |   Big Deal - Elijah [O]   | Jets        |
|   19         |   WMIC4  [Booth]      |   Snowboy- Jaden [O]      | Jets        |
|   20         |   WMIC5  [Booth]      |   A-Rab - Dylan [X]       | Jets        |
|   21         |   WMIC6  [Booth]      |   Rosalia - Evelyn [O]    | Sharks      |
|   22         |   WMIC7  [Booth]      |   Indio - Tyreek [X]      | Sharks      |
|   23         |   WMIC8  [Booth]      |   Pepe - Aristides [X]    | Sharks      |
|   24         |   BLX4R  [Booth]      |   Glad Hand               | Adults      |
|   25         |   Stage Overhead (L)  |   Ensemble/Atmosphere     |             |
|   26         |   Stage Overhead (C)  |   Ensemble/Atmosphere     |             |
|   27         |   Stage Overhead (R)  |   Ensemble/Atmosphere     |             |
|   28         |   -OPEN-              |                           |             |
|   29         |   -OPEN-              |                           |             |
|   30         |   -OPEN-              |                           |             |
|   31         |   -OPEN-              |                           |             |
|   32         |   Laptop (Music)      |                           |             |

## DCA Group Assignments

1. Principals: Maria, Tony, Riff, Bernardo, Anita
2. Jets: Action, Diesel, Baby John, Anybodys, Velma, Big Deal, Snowboy, A-Rab
3. Sharks: Chino, Francisca, Consuela, Graziella, Rosalia, Indio, Pepe
4. Adults: Krupke, Schrank, Doc, Glad Hand
