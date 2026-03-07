# West Side Story - Audio Scenes

For this show we used the Yamaha TF-5 with [TheatreMix](https://theatremix.com/) to handle scene-to-scene transitions of microphones used by on-stage performers. This allows creation of cues for audio mixing just as we use cues for lighting changes in or between scenes. All performers who must or should be mic'd must first be established on the basis of importance and presence, deprioritizing those who have fewer speaking lines or may not need a microphone, especially if there are not enough mics or headsets to go around. This should be done first to create a channel list by performer/role such as the chart see on the [primary audio page for this show](show-wss-audio.md). From there, individual performers can be assigned into a DCA (1-8) or even groups of performers can be combined--all dynamically!

## Audio Cues

To view the audio cues configured for this show please view these [screenshots from TheatreMix](files/TheatreMix - West Side Story.pdf). As this is a free-form system for configuring as you please, there's no hard rules for how to build your audio cues but this example outlines some practices that proved helpful.

* When you create a new show file you will choose the intended console model. Pick the Yamaha TF-5 which supports up to 8 DCA's.
	* Note: For WSS we used DCA 8 for overhead mics, reducing the usable channels to 7.
* Plan out your mics for performers in advance. One of the first dialogs to appear when creating a show file is the "Channels & DCAs" setup.
	* The Yahama TF-5 supports up to 32 direct inputs though TheatreMix may only default to showing the first 16. You can check the box next to channels 17-32 to enable additional channels.
	* Double-click on a channel name to set the performer or characters name. This will be shown on the scribble strip of the channel when TheatreMix is connected to the console.
	* **Channel names will be used for all scene programs so it's important to set this up before continuing!**
* Once you have configured and accepted the Channels & DCAs, you can select `File > Ensemble Setup` if you wish to create special groups for performers.
	* In the case of WSS 3 groups were configured for Sharks, Jets, and Adults. These should always be used for non-principal characters who will appear together in scenes, making it easier to assign a group to a DCA later.
* There is a padlock icon in the action bar at the top of the application window. If it is locked that will prevent any changes to the show file. Click on the icon to unlock editing, and click again to prevent accidental changes.
* Numbering for cues are set automatically but can be overriden later, and so it does require some pre-planning:
	* Use your script to identify (or create) a unique number for each scene in your production and enter those scenes first. Each new cue added will increment by a whole number.
	* However, as you create cues within each scene the number will automatically increment to place it mid-way between the last and next cue. eg. Adding a new cue between 1 and 2 will result in 1.50, adding a cue after 1.50 would be 1.75, and so on.
	* Because of this numbering scheme you may find yourself renumbering some cues as you approach the next scene number. eg. If your cue number reaches 1.99 and a cue 2.00 exists, you will not be able to add any more cues to scene 1.
* While you can technically add up to 99 cues for a scene (eg. 1.00-1.99) it is not in your besgt interest to rely on so many changes through a performance. Instead, focus on major changes involving large groups of performers.
	* It should be noted that when using these DCA assignments, any mic not in use will be immediately muted, while any mic that IS in use will be immediately unmuted!
	* When preparing for a cue change it is best to plan for which performers will be involved in a scene and prepare their mic volume ahead of moving to the new cue.
* Cue text is entirely free-form so use whatever naming or notes you wish to identify what happens during the cue.
	* You should come up with your own meaningful system for naming, starting with annotating your show script.
	* Once your cues are clearly labelled you can skip the script and use the show file as your guide!
* Use the "Clone Cue" feature to make a copy of a selected cue to keep the same performers on the same DCAs, allowing you to treat the cue text as reminder of an action to take (such as start a music track or effect, prepare for a volume change, etc.).
	* For instance, you could note the line of dialog which indicates the start of a music track.
* Once a group of performers is unmuted for a scene you can now focus on simply "riding the faders" to mix line-by-line rather than continually using cues to mute and unmute by dialog.
* If a performer will appear across multiple scenes/cues, it is best to keep them on the same DCA.
	* This is recommended even if they may be muted due to a scene change or group-mute event (eg. such as the end of a musical number where you may pause for applause).
	* The goal here is to reduce your need to look down at the console or remember if their previous fader in use now jumped to another spot or was replaced by another character's mic.
* Use color coding for cues to help identify events such as pre/post-show events, scene changes, music cues, or to just highlight certain events during the performance.
* Use the `>` symbol to indent cue descriptions. This can be useful to visually group cues within a scene.

## What is a DCA?

In short, a DCA (or Digitally Controlled Amplifier) can be a single performer or a group of performers, all controlled by a single fader. These groups can be adjusted as a whole using the fader or even muted entirely by turning off the group. However, static assignments means limited control and a need to balance both the individual performers with the group assignments. To make these more effective, TheatreMix dynamically reassigns these DCAs dynamically using the mixing console's Ethernet/WiFi capabilities.

Some notes when using DCA groups:

* Volume is additive when using DCAs. If a channel is at -5 and a DCA fader is at -10, the sum total for that channel would be -15. Think of it as applying a percentage to a percentage, where the individual channel is the "ceiling" or safe maximum volume before feedback begins.
* You MUST NOT assign any single fader to more than 1 DCA group. This can lead to unexpected volume levels if the individual channel and the DCA groups which use it are set to different levels. Also, muting of any DCA group with that channel will mute it entirely, even if the channel or another DCA group is active.
* Individual channels and DCA groups can both be given an EQ or Compressor. The benefit of using compression on a group is to ensure that all members of the DCA group are kept within range, while compression on an individual channel ensures that person in isolation is kept within range for their performance.
* When in the Groups view, the individual members are displayed to the left when a DCA group is selected. This allows access to both the group volume as a whole as well as the mic'd performers, avoiding the need for "chasing faders". Also allowis time to turn off individual channels.

To access DCA groups and assign channels manually:

* Press both INPUT1 + INPUT2 to access Groups.
* Select a group channel and press "DCA Assign" on the menu screen.
* Touch a channel name to select/deselect for the DCA group.
