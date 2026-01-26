# Audio-Video Network

This is the complete network configuration which links the tech booth to the backstage areas, providing dedicated network space for the management network, audio equipment, IP cameras, and video distribution. It connects to the general network hosted in the booth for the lighting and mixer consoles.

The network depends on a 1 gigabit (1Gbps) connection which should be more than sufficient for the expected number of IP cameras and Dante audio devices to be used. Use of Quality of Service (QoS) and Multicast (IGMP) management features will ensure data is delivered in a timely and organized manner.


## VLANs

Virtual LANs, or VLANs, represent a dedicated environment in which network traffic can be isolated from other areas. This proves useful for certain types of traffic such as Dante Audio which has certain requirements to ensure data is delivered on-time and with top priority, while other traffic such as video distribution can be considered "noisy" and may impede delivery of time-sensitive data. Think of a VLAN as a special type of express lane on the highway, where you can only enter and exit at certain points, and you may have a special pass to allow you to use that lane.

These are the VLANs associated with the full AV network:

| VLAN | Name         | Description                             | DHCP Managed?   |
|------|--------------|-----------------------------------------|-----------------|
| 1    | Management   | Default network for the booth equipment | Yes, by R7000   |
| 3    | Auto-Video   | Built-in Netgear VLAN for audio-video   | No, static only |
| 10   | Distribution | Broadcasting network for HDMI over IP   | No, static only |

These will be applied to each network switch in the form of either a Tagged (T) or Untagged (U) status on each port. This allows each port to identify as the special pass (PVID) for each toll lane (VLAN). The following guidelines should help to make this more clear:

* When a port is Untagged (U) it means that any traffic will by default belong to that VLAN.
* Only 1 VLAN may be Untagged for any given port.
* The use of a Tagged (T) VLAN means that any traffic that belongs to that VLAN is allowed to merge into and use the same toll lane--basically allowing traffic from the Untagged plus any Tagged VLANs to travel together.
* If a port is neither Untagged nor Tagged, it is essentially closed for traffic.


## Netgear GS748Tv4h2

**IP:** 192.168.1.6 (Management Network)

| Port | VLAN 1 | VLAN 3 | VLAN 10 | PVID | Name/Description | Device IP     |   |   |
|------|--------|--------|---------|------|------------------|---------------|---|---|
| 1    | U      | T      | T       | 1    | Uplink to GS716T |               |   |   |
| 2    | U      |        |         | 1    | LEA Connect 704  | 192.168.1.3   |   |   |
| 3    |        | U      |         | 3    | Yamaha NY64-D    | Link-Local    |   |   |
| 4    |        | U      |         | 3    | Booth iMac       | 192.168.3.50  |   |   |
| 5    |        | U      |         | 3    | - Available -    |               |   |   |
| 6    |        | U      |         | 3    | - Available -    |               |   |   |
| 7    |        | U      |         | 3    | - Available -    |               |   |   |
| 8    |        | U      |         | 3    | - Available -    |               |   |   |
| 9    |        | U      |         | 3    | Tech Booth       | 192.168.3.110 |   |   |
| 10   |        | U      |         | 3    | Stage View       | 192.168.3.120 |   |   |
| 11   |        | U      |         | 3    | - Available -    |               |   |   |
| 12   |        | U      |         | 3    | - Available -    |               |   |   |
| 13   |        | U      |         | 3    | - Available -    |               |   |   |
| 14   |        | U      |         | 3    | - Available -    |               |   |   |
| 15   |        | U      |         | 3    | - Available -    |               |   |   |
| 16   |        | U      |         | 3    | - Available -    |               |   |   |
| 17   |        | U      |         | 3    | - Available -    |               |   |   |
| 18   |        | U      |         | 3    | - Available -    |               |   |   |
| 19   |        | U      |         | 3    | - Available -    |               |   |   |
| 20   |        | U      |         | 3    | - Available -    |               |   |   |
| 21   |        | U      |         | 3    | - Available -    |               |   |   |
| 22   |        | U      |         | 3    | - Available -    |               |   |   |
| 23   |        | U      |         | 3    | - Available -    |               |   |   |
| 24   |        | U      |         | 3    | - Available -    |               |   |   |
| 25   |        | U      |         | 3    | - Available -    |               |   |   |
| 26   |        | U      |         | 3    | - Available -    |               |   |   |
| 27   |        | U      |         | 3    | - Available -    |               |   |   |
| 28   |        | U      |         | 3    | - Available -    |               |   |   |
| 29   |        | U      |         | 3    | - Available -    |               |   |   |
| 30   |        | U      |         | 3    | - Available -    |               |   |   |
| 31   |        | U      |         | 3    | - Available -    |               |   |   |
| 32   |        | U      |         | 3    | - Available -    |               |   |   |
| 33   |        | U      |         | 3    | - Available -    |               |   |   |
| 34   |        | U      |         | 3    | - Available -    |               |   |   |
| 35   |        | U      |         | 3    | - Available -    |               |   |   |
| 36   |        | U      |         | 3    | - Available -    |               |   |   |
| 37   |        | U      |         | 3    | - Available -    |               |   |   |
| 38   |        | U      |         | 3    | - Available -    |               |   |   |
| 39   |        | U      |         | 3    | - Available -    |               |   |   |
| 40   |        | U      |         | 3    | - Available -    |               |   |   |
| 41   |        | U      |         | 3    | - Available -    |               |   |   |
| 42   |        | U      |         | 3    | - Available -    |               |   |   |
| 43   |        |        | U       | 10   | Blackbird TX     | 192.168.10.10 |   |   |
| 44   |        |        | U       | 10   | HDMI over IP     |               |   |   |
| 45   |        |        | U       | 10   | HDMI over IP     |               |   |   |
| 46   |        |        | U       | 10   | HDMI over IP     |               |   |   |
| 47   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 48   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 49   |        |        |         |      | SFP - Not Used   |               |   |   |
| 50   |        |        |         |      | SFP - Not Used   |               |   |   |


## Netgear GS716Tv3

**IP:** 192.168.1.8 (Management Network)

| Port | VLAN 1 | VLAN 3 | VLAN 10 | PVID | Name/Description | Device IP     |   |   |
|------|--------|--------|---------|------|------------------|---------------|---|---|
| 1    | U      | T      | T       | 1    | Uplink to GS748T |               |   |   |
| 2    | U      | T      | T       | 1    | Future Uplink    |               |   |   |
| 3    |        | U      |         | 3    | Yamaha Tio1608-D | Link-Local    |   |   |
| 4    |        | U      |         | 3    | - Available -    |               |   |   |
| 5    |        | U      |         | 3    | Wing - Right     | 192.168.3.130 |   |   |
| 6    |        | U      |         | 3    | Wing - Left      | 192.168.3.140 |   |   |
| 7    |        | U      |         | 3    | - Available -    |               |   |   |
| 8    |        | U      |         | 3    | - Available -    |               |   |   |
| 9    |        |        | U       | 10   | Blackbird RX     | 192.168.10.x  |   |   |
| 10   |        |        | U       | 10   | Blackbird RX     | 192.168.10.x  |   |   |
| 11   |        |        | U       | 10   | HDMI over IP     |               |   |   |
| 12   |        |        | U       | 10   | HDMI over IP     |               |   |   |
| 13   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 14   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 15   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 16   | U      |        | T       | 1    | Admin Access     |               |   |   |
| 17   |        |        |         |      | SFP - Not Used   |               |   |   |
| 18   |        |        |         |      | SFP - Not Used   |               |   |   |


## Switch Settings

The following settings must be applied to both switches unless otherwise noted.

### Global Options

* Disable Energy Efficient Ethernet (EEE)
* Disable Green Ethernet (if available)
* Disable DHCP Relay (everywhere)
* Disable the "Auto-Video" option for VLAN 3

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

### QoS

* Enable, specifically for VLAN 3
* Global Trust: DSCP
    * DSCP 46: Clock
    * DSCP 34: Audio
* Scheduler Type: Strict (ports 1, 3-47)
    * Ensure that Dante traffic always wins
    * Sacrifices video if necessary
* No per-port limiting on Dante ports
    * Set resolution and bitrates on cameras