# Lighting Equipment

## ETC Ion XE 20

**Software Version:** 3.3.2.36 (as of December 2025)

[Product Info](https://www.etcconnect.com/Products/Consoles/Eos-Consoles/Ion-Xe/Features.aspx?LangType=1033)

[Online Manual](https://www.etcconnect.com/WebDocs/Controls/EosFamilyOnlineHelp/en-us/Default.htm)

[EOS Remote](https://apps.apple.com/us/app/eos-remote/id1479413314)

[Eos Video Learning Series](https://youtu.be/4joUizLBXAg?feature=shared)

## Network

* **Port 1 IP:** 10.101.100.30 - Touchscreen controls (booth/backstage)
  * Attaches to an ethercon panel with a P-TS7-PE touchscreen panel in the booth, and another touchscreen backstage.
  * These devices use PoE to power the devices.
* **Port 2 IP:** 192.168.1.4 - Theatre network control via ETCNomad
  * In order to use the EOS software you must have the ETC Dongle (USB) inserted into the computer.
  * “Network Devices” should see the Ion Xe console online, and can launch a show file as a remote console.

### Configure Networking

From the Eos Application (Show Mode):

1. Press the Displays softkey (bottom left of the screen)
2. `{Exit}` "Exit to Shell" (OK) - Show is saved, now in Eos Shell
3. From the Welcome screen go to `[Settings]` —> `[Network]` (left-hand column)

Within the Network Settings (or Ethernet) Section:

* IP: 192.168.1.4/255.255.255.0
* GW: 192.168.1.1
* Enable Net3 Service
* Enable sACN Output
* Enable Net3 Discovery
* Enable Mobile Apps
* `[Accept]`

Return to `[Settings]` and go to `[General]` (Show Control)

* Console Type/Role, Set to Primary
* Enable OSC
* Note or Set the ports for OSC RX (8000), OSC TX (8001)
* `[Accept and Exit]` to Relaunch EOS

Under a section Mobile Apps:

* Enable: Allow App Connections
* Enable: Visible to Mobile Apps

## Stage Lights

In-House: 9 Spots, 4 Movers, ? Pars

[ETC ColorSource Spot V](https://www.etcconnect.com/Products/Entertainment-Fixtures/ColorSource-Spot-V/Features.aspx?LangType=1033)

## Accessories

**S4LED-SFD - ETC Source Four LED Soft Focus Diffuser**

The Soft Focus Diffuser is a diffuser that is an accessory for Source Four LED fixtures. The Soft Focus Diffuser fits into a standard A-size pattern holder and delivers beautiful homogenized light when not in sharp focus. Also, use with patterns for dappled and blurry projects.

## Resources

### Patching DMX Addresses to Channels

**Terminology**

* PSD = Playback Status Display
* CIA = Central Information Area
* Universe 1 = Stage Lights
* Universe 2 = On-Stage Lights

**Enter Patch Menu**

1. New Tab -> Select Patch
2. Press "Format" button to switch between channel/address views
3. Press "Data" button to cycle through address view by universe

**For the Chauvet DMX 4-Channel Dimmer:**

2. Patch channels 180-183 directly to addresses 2/180-183
3. Labeled as Chauvet Ch#

**For the Conventional Lights (Spot 4's):**

1. Patch channels 156-160 to addresses as listed:
    * 156: 1/10
    * 157: 1/8
    * 158: 1/6
    * 159: 1/1
    * 160: 1/3

### Modify Lights in Live Area

`[Live]`

### Go to Top of Show

1. `[Go to Cue] [Out] [Enter]` - Will set all non-intensity parameters to 0 (re-home movers)
2. `[Go to Cue] [0] [Enter]` - Will leave all non-intensity parameters alone (no re-home)
3. `[Go/Play]` to begin at Cue 1

`[Go to Cue] [Enter]` - Resets the current cue
`[Go to Cue] <number> [Enter]` - Go directly to cue, using set timing

### Update a Cue

1. `[Go to Cue] <number> [Enter]` - Go to desired cue
2. `<make any changes>`
3. `[Update] [Enter]` - Modifies current and future cues
4. `[Update] [CueOnly] [Enter]` - Modifies only the current cue

### Park Lights - Locks the value of a channel

* `<channel number, combo, or thru> [At] [Out] [Park] [Enter]`
* `[Park] [Enter]` - Prompts to un-park any parked channels