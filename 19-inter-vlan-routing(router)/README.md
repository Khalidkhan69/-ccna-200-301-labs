# Lab 19: Inter-VLAN Routing Using a Router (Router-on-a-Stick)

## Overview

This lab demonstrates how to configure inter-VLAN routing using a Cisco router connected to a switch through a trunk link. The router uses subinterfaces and IEEE 802.1Q encapsulation to route traffic between multiple VLANs over a single physical router interface.

## Objectives

- Create and configure VLANs on a switch
- Assign switch access ports to the appropriate VLANs
- Configure an IEEE 802.1Q trunk link between the switch and router
- Create router subinterfaces for different VLANs
- Configure VLAN encapsulation and IP addresses on router subinterfaces
- Assign default gateways to end devices
- Verify trunk, VLAN and routing configurations
- Test communication between devices in different VLANs

## Key Concepts

### Inter-VLAN Routing

Inter-VLAN routing allows devices in different VLANs to communicate. Since VLANs are separate broadcast domains, traffic between them must be routed by a Layer 3 device.

### Router-on-a-Stick

Router-on-a-Stick is a network design in which a single physical router interface handles traffic for multiple VLANs using logical subinterfaces. The switch port connected to the router operates as a trunk.

### Router Subinterface

A subinterface is a logical interface created under a physical router interface. Each subinterface can be assigned to a different VLAN and configured with an IP address that serves as that VLAN's default gateway.

### IEEE 802.1Q Encapsulation

IEEE 802.1Q adds VLAN identification to Ethernet frames carried over a trunk link. On Cisco routers, the `encapsulation dot1Q` command associates a subinterface with a VLAN ID.

## Example VLAN Configuration

Create and name the VLANs on the switch:

```text
Switch(config)# vlan 10
Switch(config-vlan)# name SALES
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name IT
Switch(config-vlan)# exit
```

## Example Access-Port Configuration

Assign end-device ports to their respective VLANs:

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

## Example Trunk Configuration

Configure the switch interface connected to the router as a trunk. Replace `gigabitEthernet 0/1` with the actual interface in your topology.

```text
Switch(config)# interface gigabitEthernet 0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20
Switch(config-if)# no shutdown
Switch(config-if)# exit
```

## Example Router Subinterface Configuration

The following example uses `gigabitEthernet 0/0` as the router's physical interface connected to the switch.

```text
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/0.10
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 192.168.10.1 255.255.255.0
Router(config-subif)# exit

Router(config)# interface gigabitEthernet 0/0.20
Router(config-subif)# encapsulation dot1Q 20
Router(config-subif)# ip address 192.168.20.1 255.255.255.0
Router(config-subif)# exit
```

Each subinterface uses the VLAN ID corresponding to its `encapsulation dot1Q` command. The IP addresses serve as default gateways for devices in the respective VLANs.

**Note:** These are example commands and addresses. Use the interface names, VLAN IDs and IP addressing scheme from your actual Packet Tracer topology. Configure the router-connected switch port as a trunk, and ensure the allowed VLAN list includes all required VLANs.

## Verification Commands

### On the Switch

```text
show vlan brief
show interfaces trunk
show interfaces switchport
show running-config
```

### On the Router

```text
show ip interface brief
show ip route
show running-config
show interfaces gigabitEthernet 0/0
```

## Testing

- Verify that each end device is connected to the correct access VLAN.
- Confirm that the switch-to-router link is operating as a trunk.
- Check that each router subinterface has the correct VLAN encapsulation and IP address.
- Configure each end device with an IP address from its VLAN subnet and the correct default gateway.
- Use `ping` to test communication between devices in different VLANs.
- If connectivity fails, check the trunk configuration, VLAN assignments, router subinterfaces, IP addresses and default gateways.

## Files

- `inter-vlan-routing(router).pkt` — Cisco Packet Tracer lab file

## Tools

- Cisco Packet Tracer
- Cisco IOS CLI