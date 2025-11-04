# Theatre Lighting

## Console

ETC Ion XE 20
https://www.etcconnect.com/WebDocs/Controls/EosFamilyOnlineHelp/en-us/Default.htm
https://www.etcconnect.com/Products/Consoles/Eos-Consoles/Ion-Xe/Features.aspx?LangType=1033
https://www.etcconnect.com/WorkArea/DownloadAsset.aspx?id=10737492144

## Lights

[ETC ColorSource Spot V](https://www.etcconnect.com/Products/Entertainment-Fixtures/ColorSource-Spot-V/Features.aspx?LangType=1033)

In-House: 9 Spots, 4 Movers, ? Pars

## Accessories

**S4LED-SFD - ETC Source Four LED Soft Focus Diffuser**

The Soft Focus Diffuser is a diffuser that is an accessory for Source Four LED fixtures. The Soft Focus Diffuser fits into a standard A-size pattern holder and delivers beautiful homogenized light when not in sharp focus. Also, use with patterns for dappled and blurry projects.

**Canto 1200 MSR Followspot MK2**

* 120V @ 15 Amp Service
* https://cantousa.com/followspots/
* https://cantousa.com/followspots/msr-followspots/
* https://dy9zop0zwp6br.cloudfront.net/2020/06/Canto_1200MSR_040125_V01_3.pdf
* https://dy9zop0zwp6br.cloudfront.net/2021/02/EzWCKeYc-CantoUSA_1200_MSRFF_120V_MK2_Followspot_User_Manual_022521_V01.pdf

Replacement Bulb:
Per the manual, 1200W 6000K Philips 1200 MSR Gold FastFit PGJX50 750 hrs lamp
Philips 28688-0 1200W

## Resources

https://apps.apple.com/us/app/eos-remote/id1479413314

[Eos Video Learning Series](https://youtu.be/4joUizLBXAg?feature=shared)


## Patching DMX Addresses to Channels

### Terminology

PSD = Playback Status Display
CIA = Central Information Area

### Processes

New Tab -> Select Patch
Press “Format” button to switch between channel/address views
Press “Data” button to cycle through address view by universe

Stage Lights: Universe 1
On-Stage Lights: Universe 2

Chauvet DMX 4-Channel Dimmer
Patch channels 180-183 directly to addresses 2/180-183
Labeled as Chauvet Ch#

Conventional Lights (Spot 4’s)
Patch channels 156-160 to addresses as listed:
156: 1/10
157: 1/8
158: 1/6
159: 1/1
160: 1/3


**Modify Lights in Live Area**

[Live]


**Go to Top of Show**

[Go to Cue] [Out] [Enter] - Will set all non-intensity parameters to 0 (re-home movers)
[Go to Cue] [0] [Enter] - Will leave all non-intensity parameters alone (no re-home)
[Go/Play] to begin at Cue 1

[Go to Cue] [Enter] - Resets the current cue
[Go to Cue] <number> [Enter] - Go directly to cue, using set timing


**Update a Cue**

[Go to Cue] <number> [Enter] - Go to desired cue
<make any changes>
[Update] [Enter] - Modifies current and future cues
[Update] [CueOnly] [Enter] - Modifies only the current cue


**Park Lights - Locks the value of a channel**

<channel number, combo, or thru> [At] [Out] [Park] [Enter]
[Park] [Enter] - Prompts to un-park any parked channels