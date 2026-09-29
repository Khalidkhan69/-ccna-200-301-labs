# Lab 09 - RIP Dynamic Routing

## Overview

This lab demonstrates dynamic routing using the Routing Information Protocol (RIP). Routers exchange routing information and automatically learn paths to remote networks.

## Objectives

- Configure RIP dynamic routing
- Advertise directly connected networks
- Configure RIPv2
- Disable automatic summarization
- Verify dynamically learned routes
- Test connectivity between remote networks

## Basic Configuration

```cisco
router rip
version 2
no auto-summary
network <directly-connected-network>
```

## Verification Commands

```cisco
show ip route
show ip protocols
show running-config
ping <destination-ip-address>
```

RIP-learned routes appear with the letter `R` in the routing table.

## Tool Used

- Cisco Packet Tracer

## Lab File

- `rip-dynamic-routing.pkt`