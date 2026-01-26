# Audio-Video Network

This is the complete network configuration which links the tech booth to the backstage areas, providing dedicated network space for a management network, Dante audio equipment, a link to the lighting console, feeds from IP cameras, and video distribution. It connects to the general network hosted in the booth for the lighting and mixer consoles.

The network depends on a 1 gigabit (1Gbps) connection which should be more than sufficient for the expected number of IP cameras and Dante audio devices to be used. It uses Quality of Service (QoS) and Multicast (IGMP) management features to ensure data is delivered in a timely and organized manner.


## VLAN Assignments

A Virtual LANs, or `VLAN`, represents a dedicated environment in which network traffic can be isolated. This is extremely useful for certain types of traffic such as Dante Audio which has strict requirements to ensure data is delivered on-time and with top priorit. Meanwhile, other traffic such as video distribution can be considered "noisy" and may impede delivery of time-sensitive data. Think of a VLAN as an express lane on the highway, where you can only enter and exit at certain points (ports), and you may have a special "toll pass" to allow you to use that lane (Port VLAN ID, or `PVID`).

These are the VLANs associated with the complete AV network:

| VLAN | Name         | Description                             | DHCP Managed?       |
|------|--------------|-----------------------------------------|---------------------|
| 1    | Management   | Default network for the booth equipment | Yes, by R7000       |
| 3    | Auto-Video   | Built-in Netgear VLAN for audio-video   | No, static IPs only |
| 10   | Distribution | Broadcasting network for HDMI over IP   | No, static IPs only |

These VLANs will be assigned within each network switch by either a Tagged (T) or Untagged (U) status on each port. This allows the port to identify traffic using the special "toll pass" (PVID) for each "toll lane" (VLAN). The following guidelines should help to make this more clear:

* When a port is `Untagged` (U) it means that any traffic may travel in that VLAN.
* By default, any traffic which does not have a VLAN ID will be assumed to be VLAN 1.
* When a port is `Tagged` (T) id means that any traffic which belongs to that VLAN is allowed to move across that port.
* Only 1 VLAN may be `Untagged` for any given port, but many VLANs may be `Tagged` for a port.
* A port which contains both `Untagged` and multiple `Tagged` VLANs is considered a `trunk port`.
* If a port is neither `Untagged` nor `Tagged`, it is essentially closed for any traffic.
* For an `Untagged` port, specifying a `PVID` means to apply that VLAN ID to all egress (outbound) traffic.

In the following switch configurations, there are 2 `trunk ports` to allow the switches to connect to each other. By convention port #1 is used as the `uplink` between the tech booth switch and backstage switch.

## IP Addresses

In order for devices to speak to each other they must also utilize an IP address which can be automatically assigned (DHCP) or manually assigned (Static), and these values use a specific prefix for common address space which identifies a network range consisting of 4 groups of numbers (quads). In continuing the analogy of vehicles and toll lanes, think of this as the license plate for a vehicle:

* The first 2 "quads" represent the network range (eg. "192.168").
	* Think of this as the state that issued the license plate.
* By convention we use a 3rd quad for a "subnet" matching the VLAN.
	* Think of this as the county in the state which issued the license plate.
* The final number (4th quad) in the IP address identifies a device within the subnet.
	* And just like a license plate every IP address must be **unique** for each device!

In addition to an IP address each device uses a `Subnet Mask` which is a value that says what networks can talk to other networks. For the case of this network we only want devices on the same subnet to speak with each other so we use a common default of `255.255.255.0` which means only devices which share the first 3 quads of their address can speak to each other under normal conditions.

The only other way devices can talk across networks is to introduce a router or "gateway" which is aware of other networks and how to reach them. In the case of the AV network only the devices which belong to the Management (default) VLAN will use a gateway, which is the IP address of the [R7000 router](network-general.md): `192.168.1.1`.

**Special Note:** For our Dante Audio devices, these have a special fallback protocol called "Link-Local". In the absence of a static IP assignment, and no available DHCP server to dynamically assign an IP address, the devices will self-negotiate their IP address among themselves. This uses a special network range 169.254.0.0 through 169.254.255.255 and so this space must be kept clear of any other devices to avoid conflict.


## Netgear GS748Tv4h2

**Location:** Tech Booth

**IP:** 192.168.1.6 (Management Network)

| Port | VLAN 1 | VLAN 3 | VLAN 10 | PVID | Name/Description | Device IP     | Purpose/Notes     |
|------|--------|--------|---------|------|------------------|---------------|-------------------|
| 1    | U      | T      | T       | 1    | Trunk Port       |               | Uplink to GS716T  |
| 2    | U      |        |         | 1    | LEA Connect 704  | 192.168.1.3   | House Amp Control |
| 3    |        | U      |         | 3    | Yamaha NY64-D    | Link-Local    | Dante Audio       |
| 4    |        | U      |         | 3    | Booth iMac       | 192.168.3.50  | OBS, Video Output |
| 5    |        | U      |         | 3    | - Available -    |               |                   |
| 6    |        | U      |         | 3    | - Available -    |               |                   |
| 7    |        | U      |         | 3    | - Available -    |               |                   |
| 8    |        | U      |         | 3    | - Available -    |               |                   |
| 9    |        | U      |         | 3    | Tech Booth       | 192.168.3.110 | AVer PTZ310       |
| 10   |        | U      |         | 3    | Stage View       | 192.168.3.120 | AVer PTZ300N      |
| 11   |        | U      |         | 3    | - Available -    |               |                   |
| 12   |        | U      |         | 3    | - Available -    |               |                   |
| 13   |        | U      |         | 3    | - Available -    |               |                   |
| 14   |        | U      |         | 3    | - Available -    |               |                   |
| 15   |        | U      |         | 3    | - Available -    |               |                   |
| 16   |        | U      |         | 3    | - Available -    |               |                   |
| 17   |        | U      |         | 3    | - Available -    |               |                   |
| 18   |        | U      |         | 3    | - Available -    |               |                   |
| 19   |        | U      |         | 3    | - Available -    |               |                   |
| 20   |        | U      |         | 3    | - Available -    |               |                   |
| 21   |        | U      |         | 3    | - Available -    |               |                   |
| 22   |        | U      |         | 3    | - Available -    |               |                   |
| 23   |        | U      |         | 3    | - Available -    |               |                   |
| 24   |        | U      |         | 3    | - Available -    |               |                   |
| 25   |        | U      |         | 3    | - Available -    |               |                   |
| 26   |        | U      |         | 3    | - Available -    |               |                   |
| 27   |        | U      |         | 3    | - Available -    |               |                   |
| 28   |        | U      |         | 3    | - Available -    |               |                   |
| 29   |        | U      |         | 3    | - Available -    |               |                   |
| 30   |        | U      |         | 3    | - Available -    |               |                   |
| 31   |        | U      |         | 3    | - Available -    |               |                   |
| 32   |        | U      |         | 3    | - Available -    |               |                   |
| 33   |        | U      |         | 3    | - Available -    |               |                   |
| 34   |        | U      |         | 3    | - Available -    |               |                   |
| 35   |        | U      |         | 3    | - Available -    |               |                   |
| 36   |        | U      |         | 3    | - Available -    |               |                   |
| 37   |        | U      |         | 3    | - Available -    |               |                   |
| 38   |        | U      |         | 3    | - Available -    |               |                   |
| 39   |        | U      |         | 3    | - Available -    |               |                   |
| 40   |        | U      |         | 3    | - Available -    |               |                   |
| 41   |        | U      |         | 3    | - Available -    |               |                   |
| 42   |        | U      |         | 3    | - Available -    |               |                   |
| 43   |        |        | U       | 10   | Blackbird TX     | 192.168.10.10 | HDMI Signal Out   |
| 44   |        |        | U       | 10   | HDMI over IP     |               |                   |
| 45   |        |        | U       | 10   | HDMI over IP     |               |                   |
| 46   |        |        | U       | 10   | HDMI over IP     |               |                   |
| 47   | U      |        | T       | 1    | Admin Access     |               |                   |
| 48   | U      |        | T       | 1    | Admin Access     |               |                   |
| 49   |        |        |         |      | SFP - Not Used   |               |                   |
| 50   |        |        |         |      | SFP - Not Used   |               |                   |


## Netgear GS716Tv3

**Location:** Backstage

**IP:** 192.168.1.8 (Management Network)

| Port | VLAN 1 | VLAN 3 | VLAN 10 | PVID | Name/Description | Device IP     | Purpose/Notes     |
|------|--------|--------|---------|------|------------------|---------------|-------------------|
| 1    | U      | T      | T       | 1    | Trunk Port       |               | Uplink to GS748T  |
| 2    | U      | T      | T       | 1    | Future Uplink    |               |                   |
| 3    |        | U      |         | 3    | Yamaha Tio1608-D | Link-Local    | Dante Audio       |
| 4    |        | U      |         | 3    | - Available -    |               |                   |
| 5    |        | U      |         | 3    | Wing - Right     | 192.168.3.130 | AVer PTZ300N      |
| 6    |        | U      |         | 3    | Wing - Left      | 192.168.3.140 | AVer PTZ300N      |
| 7    |        | U      |         | 3    | - Available -    |               |                   |
| 8    |        | U      |         | 3    | - Available -    |               |                   |
| 9    |        |        | U       | 10   | Blackbird RX     | 192.168.10.x  | HDMI Signal In    |
| 10   |        |        | U       | 10   | Blackbird RX     | 192.168.10.x  | HDMI Signal In    |
| 11   |        |        | U       | 10   | HDMI over IP     |               |                   |
| 12   |        |        | U       | 10   | HDMI over IP     |               |                   |
| 13   | U      |        | T       | 1    | Admin Access     |               |                   |
| 14   | U      |        | T       | 1    | Admin Access     |               |                   |
| 15   | U      |        | T       | 1    | Admin Access     |               |                   |
| 16   | U      |        | T       | 1    | Admin Access     |               |                   |
| 17   |        |        |         |      | SFP - Not Used   |               |                   |
| 18   |        |        |         |      | SFP - Not Used   |               |                   |


## Switch Settings

The following settings must be applied to both switches unless otherwise noted.

### Global Options

* Disable Energy Efficient Ethernet (EEE)
* Disable Green Ethernet (if available)
* Disable DHCP or DHCP Relay (if available)
* Disable the "Auto-Video" option for the built-in VLAN 3

### IGMP Snooping

* Enable IGMP Snooping Status
* Disable Validate IGMP IP Header
* Disable Block Unknown Multicast Address
* Enable Snooping Admin Mode
* IGMP Snooping Interface Configuration
    * Enable Admin Mode for ports by switch
    * GS418T
        * Enable for Ports 1, 3-46
        * Disable for Ports 2, 47-50
    * GS716T
        * Enable for Ports 1-14
        * Disable for Ports 15-18
* IGMP Snooping VLAN Configuration (VLANs 3 and 10)
    * VLAN <id>
    * Disable Fast Leave Admin Mode
    * Host Timeout: 260
    * Maximum Response Time: 10
    * MRouter Timeout: 255
    * Query Mode: Enable (GS748T only, Disable for GS716T)
    * Query Interval: 125

### IGMP Snooping Querier

* GS748T
    * Enable IGMP Querier, IP 0.0.0.0
    * Enable for VLANs 3 and 10
        * VLAN 3: 192.168.3.1
        * VLAN 10: 192.168.10.1
* GS716T
    * Disable IGMP Querier
    * Confirm as non-participating or non-querier

### Quality of Service (QoS)

* Enable, specifically for VLAN 3
* Global Trust: DSCP
    * DSCP 46: Clock
    * DSCP 34: Audio
* Scheduler Type: Strict
 		* For GS748T: ports 1, 3-44
		* For GS716T: ports 1-8
    * Ensures that Dante traffic always wins
    * Sacrifices video if necessary
* Do not specify per-port rate limiting (ingress or egress) on ports
    * Set resolution and bitrates on cameras for speed limits, not at the switch!
