# Lighting Tech Lab - Tech Specs

## ETC Element

### Hardware Info

- P/N: 4330A1020
- S/N: 434401707
- Runs: Windows XP
- Shipped: 2009-2014
- Out of Service: 2023
- Addresses: 512
- Eos Version: 2.9.3.23
- OS: Windows XP

### Monitor Support

- Maximum: 2 Multi-Touch, DVI Monitors
	- Note: can use DVI to HDMI adapters, if needed
- Max Resolution: 1920x1080
	- Display 1: 20” Acer X203H 1600x900
	- Display 2: 19” Lenovo ThinkVision L192wA 1440x90
- Use `Ctrl+Alt+F12` to open the graphics preferences to extend/swap displays

### Storage

The ETC Element originally shipped with a 1TB HDD which only used 2 primary partitions: a C drive (10GB) for the OS and a D drive (25GB) for user files. A third partition of 35GB is used by the OS. This has been replaced with a modern 240GB SSD by cloning the original drive partitions and copying the contents onto the new drive's partitions. Use of Windows XP means any replacement drive just needs to be partitioned in the same manner and use MBR for booting.

```
diskpart

select disk Y
clean
convert mbr

create partition primary size=10240
format fs=ntfs quick label="ETC"
active
assign letter=X

create partition primary size=25600
format fs=ntfs quick label="USER"
assign letter=Y

create partition primary size=38912
set id=45 override

exit
```

## Sample Fixture

Generic 7-Channel RGB LED Light Bar w/ Built-in Effects

> Note: DMX doesn’t send commands—it sends values, and ranges turn those values into behavior.
Ranges act as buffers, so small signal changes or imprecise control don’t accidentally switch modes.

### DMX Behavior

* CH1: R, 0-255 Dimming, 0=Off
* CH2: G, 0-255 Dimming, 0=Off
* CH3: B, 0-255 Dimming, 0=Off
* CH4: Mode/Program Select
  * No. - DMX Value - Function
  * 1 - 0-11 - Off —> No Program Active, Manual RGB Mode
  * 2 - 12-23 - Red
  * 3- 24-35 - Green
  * 4 - 36-47 - Blue
  * 5 - 48-59 - Yellow
  * 6 - 60-71 - Purple
  * 7 - 72-83 - Cyan
  * 8 - 84-95 - White
  * 9 - 96-107 - Program01
  * 10 - 108-119 - Program02
  * 11 - 120-131 - Program03
  * 12 - 132-143 - Program04
  * 13 - 144-155 - Program05
  * 14 - 156-167 - Program06
  * 15 - 168-179 - Program07
  * 16 - 180-191 - Program08
  * 17 - 192-203 - Program09
  * 18 - 204-215 - Program10
  * 19 - 216-227 - Program11
  * 20 - 228-239 - Program12
  * 21 - 240-251 - Program13
  * 22 - 252-255 - Sound Mode
* CH5: Speed, 0-255, Sensitivity 0-255
* CH6: Flash, 0-4 Off, Flash 5-255
* CH7: Master Dimmer, 0-255 Dimming (0=Off)

### Channel Modes

* DMX Mode 1: A001-A512
* DMX Mode 2: d001-d512
* DMX Mode 3: C001-C512
* DMX Mode 4: E001-E512
* DMX Mode 5: P001-P512
* DMX Mode 6: H001-H512

### Manual/Program Modes

* Manual Red Dimmer: r000-r255
* Manual Green Dimmer: G000-G255
* Manual Blue Dimmer: b000-b255
* Strobe: F500-F520
* Program 1: 1E00-1E20
* Program 2: 2E00-2E20
* Program 3: 3E00-3E20
* Program 4: 4E00-4E20
* Program 5: 5E00-5E20
* Program 6: 6E00-6E20
* Program 7: 7E00-7E20
* Program 8: 8E00-8E20
* Program 9: 1F00-1F20
* Program 10: 2F00-2F20
* Program 11: 3F00-3F20
* Program 12: 4F00-4F20
* Program 13: EF00-EF20
* Sound: SU00-SU20