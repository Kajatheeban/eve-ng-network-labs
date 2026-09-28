# Palo Alto Firewall & VLAN Lab - EVE-NG

## About

This is one of my networking labs created in **EVE-NG** using a **Palo Alto firewall, switch, and VPCS**.

The main purpose of this lab was to practice VLAN segmentation and Palo Alto firewall configuration.

## Topology


                         WAN
                          |
                          |
                  +---------------+
                  |  Palo Alto FW  |
                  |               |
                  | WAN           |
                  | MGMT          |
                  | VLAN Subifs   |
                  +-------+-------+
                          |
                       Trunk
                          |
                  +-------+-------+
                  |    Switch     |
                  +---+---+---+---+
                      |   |   |
                    VLAN VLAN VLAN
                     101 102 103
                      |   |   |
                    VPC1 VPC2 VPC3
```

## What I configured

### Palo Alto Firewall

* WAN interface
* Management interface
* Layer 3 subinterfaces for VLANs
* Security zones
* Security policies
* Source NAT
* Routing

### Switch

* VLAN 101
* VLAN 102
* VLAN 103
* Access ports
* Trunk port
* 802.1Q VLAN tagging

### VPCS

Used VPCS as the end devices to test connectivity between the VLANs and the firewall.

Some of the commands used for testing:

```text
show ip
ping <destination-ip>
trace <destination-ip>
```

## VLANs

| VLAN | Network         |
| ---- | --------------- |
| 101   | VLAN 101 network |
| 102   | VLAN 102 network |
| 103  | VLAN 103 network |

The Palo Alto subinterfaces are used as the default gateways for the VLANs.

```text
ethernet1/2.101 → VLAN 101
ethernet1/2.102 → VLAN 102
ethernet1/2.103 → VLAN 103
```

## Testing

I tested:

* VLAN connectivity
* VPC to firewall gateway connectivity
* Inter-VLAN connectivity
* WAN connectivity
* NAT
* Security policy behavior
* Traceroute
* Firewall management access

## Files

```text
eve-ng/
└── palo-alto-vlan-lab.unl

configurations/
├── palo-alto/
└── switch/

screenshots/
└── topology.png
```

## Tools

* EVE-NG
* Palo Alto Networks Firewall
* Cisco/Layer 2 Switch
* VPCS

## Note

This is a personal lab created for learning and practicing network engineering and firewall configuration.

No real company or customer configurations are included.
