# Lab 18: Inter-VLAN Routing Using a Multilayer Switch

## Overview

This lab demonstrates how to configure inter-VLAN routing using a Cisco multilayer switch. Switch Virtual Interfaces (SVIs) provide Layer 3 gateways for different VLANs, allowing devices in separate VLANs to communicate through the multilayer switch.

## Objectives

- Create and configure VLANs
- Assign switch access ports to the appropriate VLANs
- Configure Switch Virtual Interfaces (SVIs)
- Assign IP addresses to SVIs to act as default gateways
- Enable IP routing on the multilayer switch
- Verify VLAN and routing configurations
- Test communication between devices in different VLANs

## Key Concepts

### Inter-VLAN Routing

Inter-VLAN routing allows devices in different VLANs to communicate with one another. Because VLANs are separate broadcast domains, communication between them requires a Layer 3 device, such as a router or multilayer switch.

### Multilayer Switch

A multilayer switch performs both Layer 2 switching and Layer 3 routing. It can route traffic between VLANs without requiring a separate external router.

### Switch Virtual Interface (SVI)

An SVI is a logical Layer 3 interface associated with a VLAN. It can provide the default gateway for devices in that VLAN.

### IP Routing

The `ip routing` command enables Layer 3 routing on supported Cisco multilayer switches, allowing traffic to be routed between configured VLAN interfaces.

## Example VLAN Configuration

Create and name the VLANs:

```text
Switch(config)# vlan 10
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name IT
Switch(config-vlan)# exit
```

## Example Access-Port Configuration

Assign access ports to their respective VLANs:

```text
Switch(config)# interface fastEthernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# exit

Switch(config)# interface fastEthernet 0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20
Switch(config-if)# exit
```

## Example SVI Configuration

Configure an SVI for each VLAN. These addresses serve as the default gateways for the devices in their respective VLANs.

```text
Switch(config)# interface vlan 10
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit

Switch(config)# interface vlan 20
Switch(config-if)# ip address 192.168.20.1 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
```

Enable Layer 3 routing:

```text
Switch(config)# ip routing
```

**Note:** These are example addresses and commands. Use the VLAN IDs, addressing scheme, and interfaces from your actual Packet Tracer topology. An SVI generally becomes operational when its VLAN exists and at least one associated Layer 2 port is active and forwarding.

## Verification Commands

```text
show vlan brief
show ip interface brief
show ip route
show interfaces vlan 10
show interfaces vlan 20
show running-config
```

## Testing

- Verify that each device belongs to the correct VLAN.
- Confirm that the VLAN interfaces are up and have the correct IP addresses.
- Configure each end device with an IP address in its VLAN subnet and the correct default gateway.
- Use `ping` to test communication between devices in different VLANs.
- Check the routing table if inter-VLAN communication fails.

## Files

- `inter-vlan-routing(mls).pkt` — Cisco Packet Tracer lab file

## Tools

- Cisco Packet Tracer
- Cisco IOS CLI