# Lab 12 - Route Redistribution

## Overview

This lab demonstrates route redistribution between different dynamic routing protocols. Redistribution allows routes learned by one routing protocol to be advertised through another routing protocol.

## Objectives

- Configure multiple dynamic routing protocols
- Redistribute OSPF routes into EIGRP
- Redistribute EIGRP routes into OSPF
- Configure an EIGRP seed metric
- Verify external routes in the routing table
- Test connectivity between different routing domains

## OSPF into EIGRP

EIGRP requires five metric values when routes are redistributed into it:

```cisco
router eigrp 100
redistribute ospf 1 metric 10000 100 255 1 1500
```

The metric values represent:

```text
Bandwidth  Delay  Reliability  Load  MTU
10000      100    255          1     1500
```

## EIGRP into OSPF

```cisco
router ospf 1
redistribute eigrp 100 subnets
```

The `subnets` keyword ensures that subnetted routes are redistributed into OSPF.

## Verification Commands

```cisco
show ip route
show ip protocols
show ip ospf neighbor
show ip eigrp neighbors
show running-config
ping <destination-ip-address>
traceroute <destination-ip-address>
```

Externally learned routes may appear as:

- `D EX` for external EIGRP routes
- `O E1` or `O E2` for external OSPF routes

## Important Note

Route redistribution must be configured carefully because incorrect configuration can cause routing loops, poor route selection or missing routes.

## Tool Used

- Cisco Packet Tracer

## Lab File

- `route-redistribution.pkt`