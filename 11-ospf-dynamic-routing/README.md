# Lab 11 - OSPF Dynamic Routing

## Overview

This lab demonstrates dynamic routing using Open Shortest Path First (OSPF). Routers form neighbor relationships, exchange link-state information and automatically learn routes to remote networks.

## Objectives

- Configure OSPF dynamic routing
- Configure an OSPF process ID
- Configure unique router IDs
- Advertise connected networks using wildcard masks
- Assign networks to an OSPF area
- Establish and verify OSPF neighbor relationships
- Verify dynamically learned routes
- Test connectivity between remote networks

## Basic Configuration

```cisco
enable
configure terminal
router ospf <process-id>
router-id <router-id>
network <network-address> <wildcard-mask> area <area-number>
end
write memory
```

The OSPF process ID is locally significant and does not need to match between neighboring routers. Each router must have a unique router ID.

## Example

```cisco
router ospf 1
router-id 1.1.1.1
network 192.168.1.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0
```

## Verification Commands

```cisco
show ip ospf
show ip ospf neighbor
show ip ospf database
show ip route ospf
show ip protocols
show running-config
ping <destination-ip-address>
```

OSPF-learned routes appear with the letter `O` in the routing table.

## Tool Used

- Cisco Packet Tracer

## Lab File

- `ospf-dynamic-routing.pkt`