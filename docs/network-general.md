# General Network

The tech booth is outfitted with a dedicated wireless network which allows access to the audio mixer and ETC lighting console via mobile and desktop computers. This affords students the ability to learn tools such as the [Yamaha TF Stagemix for iOS](https://usa.yamaha.com/products/proaudio/software/tfstagemix/index.html) or [TF Editor Software for PC/Mac](https://usa.yamaha.com/products/proaudio/software/tfeditor/index.html) to wirelessly manage the audio mixer from backstage or within the house. For ETC lighting, students can learn the Eos software with use of the [ETCnomad USB Key](https://www.etcconnect.com/ETCnomad/) to design and manage cues while acting as a remote console.

## WiFi Router - Netgear R7000

This is a private network which can access the internet through the DHS network, and is still subject to rules and protections put in place by GCPS. This is not meant to be used directly by the student body so passwords have been purposefully removed.

* **WiFi Type:** 802.11ac (WiFi 5)
* **Network Name (SSID):** DHS_Theatre
* **Network Password:** -REDACTED-
* **Gateway IP:** 192.168.1.1
* **DHCP Range:** 192.168.1.10 - 192.168.1.254
* **DNS Servers:** 1.1.1.1 / 1.0.0.1
* **Admin Account:** admin / -REDACTED-
* **Last Firmware:** Asuswrt-Merlin Xwrt-Vortex 386.7_2

### Ports

* **1** - Uplink to GS748T
* **2** - Yamaha TF-5
* **3** - ETC Ion XE 20
* **4** - LEA Connect 704
* **WAN** - Connected to DHS network

### Dynamic IP Reservations

Devices on a network need a unique identifier which is an IP Address. The R7000 offers dynamic assignments in the range of 10-254, leaving the range of 1-9 for special static assignments to specific devices. These **cannot** and **should not** be overridden by any other device!

### Static IP Assignments

* [192.168.1.1](http://192.168.1.1): **Netgear R7000**
* 192.168.1.2: **Yamaha TF-5**
* [192.168.1.3](http://192.168.1.3): **LEA Connect 704**
* 192.168.1.4: **ETC Ion XE 20**
* [192.168.1.6](http://192.168.1.6): **Netgear GS748T**
* [192.168.1.8](http://192.168.1.8): **Netgear GS716T**

### Advanced Settings

The following features should be set as noted, should the device be reset or need to be reconfigured:

* LAN —> IPTV/Multicast Routing: Enable Multicast Routing (IGMP Proxy)
* Wireless —> Professional: AP Isolation = Disabled

## Special Devices

The Yamaha TF-5 contains a special expansion NY64-D expansion card which provides a pair of RJ-45 connectors which are reserved for Dante Audio devices. The theatre uses a Yamaha Tio1608-D stagebox backstage which is directly connected using a standard ethernet cable in the building. These devices may be configured to speak directly with each other and will self-assign IP addresses using a protocol called Link-Local (or APIPA). In this process they will automatically use an IP in the special range 169.254.x.x when no DHCP server is present.

For more information about configuring Dante Audio with Yamaha devices please see the following videos.

* [YoutTube: Dante Controller](https://www.youtube.com/watch?v=zWfa3slcaQI)
* [YouTube: Patching to TF5](https://www.youtube.com/watch?v=NYP2Bn7HACE)
