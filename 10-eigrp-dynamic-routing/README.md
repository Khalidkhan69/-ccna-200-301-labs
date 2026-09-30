# Lab 10 - EIGRP Dynamic Routing

## Overview

This lab demonstrates dynamic routing using the Enhanced Interior Gateway Routing Protocol (EIGRP). Routers exchange routing information and automatically learn paths to remote networks.

## Objectives

- Configure EIGRP dynamic routing
- Configure an EIGRP autonomous system number
- Advertise directly connected networks
- Establish EIGRP neighbor relationships
- Verify dynamically learned routes
- Test connectivity between remote networks

## Basic Configuration

```cisco
enable
configure terminal
router eigrp <autonomous-system-number>
network <network-address> <wildcard-mask>
no auto-summary
end
write memory
```

The same autonomous system number must be configured on neighboring EIGRP routers.

## Verification Commands

```cisco
show ip eigrp neighbors
show ip eigrp topology
show ip route
show ip protocols
show running-config
ping <destination-ip-address>
```

EIGRP-learned routes appear with the letter `D` in the routing table.

## Tool Used

- Cisco Packet Tracer

## Lab File

- `eigrp-dynamic-routing.pkt`