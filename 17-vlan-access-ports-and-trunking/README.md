# Lab 17: VLAN Access Ports and Trunk Links

## Overview

This lab demonstrates how to create VLANs, assign switch access ports to VLANs and configure an IEEE 802.1Q trunk link between Cisco switches.

## Objectives

- Create and name VLANs
- Configure switch ports as access ports
- Assign access ports to specific VLANs
- Configure a trunk link between switches
- Allow multiple VLANs across a trunk link
- Verify VLAN membership and trunk operation
- Test communication between devices in the same VLAN

## Key Concepts

### VLAN

A VLAN logically divides a physical switch into separate broadcast domains. Devices in different VLANs cannot communicate without a router or multilayer switch.

### Access Port

An access port carries traffic for only one VLAN. It is normally connected to an end device such as a computer, printer or server.

### Trunk Link

A trunk link carries traffic for multiple VLANs between network devices. IEEE 802.1Q tagging identifies the VLAN associated with each Ethernet frame.

## Example VLAN Configuration

```cisco
Switch(config)# vlan 10
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name IT
Switch(config-vlan)# exit
```

## Example Access-Port Configuration

```cisco
Switch(config)# interface fastEthernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# exit

Switch(config)# interface fastEthernet 0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20
Switch(config-if)# exit
```

## Example Trunk Configuration

Configure the interface connecting the two switches:

```cisco
Switch(config)# interface gigabitEthernet 0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20
Switch(config-if)# no shutdown
```

The corresponding interface on the other switch must also be configured as a trunk.

## Verification Commands

```cisco
show vlan brief
show interfaces trunk
show interfaces switchport
show running-config
show mac address-table
```

## Testing

- Devices in the same VLAN should communicate across the trunk link.
- Devices in different VLANs should not communicate unless inter-VLAN routing is configured.
- Use `ping` to test connectivity between devices.

## Files

- `vlan-access-ports-and-trunking.pkt` — Cisco Packet Tracer lab file

## Tools

- Cisco Packet Tracer
- Cisco IOS CLI