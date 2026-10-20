# Lab 24 — IPv6 RIP, EIGRP, and OSPF Routing

## Overview

This lab explores dynamic IPv6 routing using RIPng, EIGRP for IPv6, and OSPFv3 in Cisco Packet Tracer.

Dynamic routing protocols allow routers to exchange routing information and learn paths to remote IPv6 networks. This lab provides practical experience with configuring and verifying IPv6 dynamic routing.

## Objectives

- Understand dynamic IPv6 routing.
- Explore RIPng, EIGRP for IPv6, and OSPFv3.
- Configure IPv6 routing on Cisco routers.
- Verify routing tables and learned IPv6 routes.
- Test connectivity between remote IPv6 networks.
- Troubleshoot IPv6 routing and connectivity issues.

## Lab File

- Cisco Packet Tracer `.pkt` file included in this folder.

## Key Concepts

- **RIPng:** A distance-vector routing protocol designed for IPv6.
- **EIGRP for IPv6:** A Cisco routing protocol that supports IPv6 route exchange.
- **OSPFv3:** A link-state routing protocol that supports IPv6.
- **Dynamic routing:** Routers automatically learn and update routes through routing protocols.
- **IPv6 routing table:** Contains routes used to forward IPv6 packets to destination networks.

## Verification Commands

### 1. Display IPv6 interfaces

```text
show ipv6 interface brief
```

Displays IPv6 addresses and interface status.

### 2. Display the IPv6 routing table

```text
show ipv6 route
```

Displays connected, static, and dynamically learned IPv6 routes.

### 3. Check RIPng configuration

```text
show ipv6 protocols
```

Displays information about active IPv6 routing protocols.

### 4. Check EIGRP neighbors

```text
show ipv6 eigrp neighbors
```

Displays EIGRP for IPv6 neighbor relationships on supported IOS implementations.

### 5. Check OSPFv3 neighbors

```text
show ipv6 ospf neighbor
```

Displays OSPFv3 neighbor relationships.

### 6. Test IPv6 connectivity

```text
ping ipv6-address
```

Replace `ipv6-address` with the destination device's IPv6 address.

## Expected Results

- IPv6 addresses are configured on the appropriate router interfaces.
- The configured routing protocol learns routes to remote IPv6 networks.
- Routing tables display the available IPv6 routes.
- Neighbor relationships form where protocol configuration and network conditions permit.
- End devices can communicate across remote IPv6 networks when routing and return paths are configured correctly.

Actual results depend on the topology, router models, IOS features, and configuration in the Packet Tracer file.

## Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv6 addressing
- RIPng
- EIGRP for IPv6
- OSPFv3
- Dynamic routing and route verification

## Learning Outcome

This lab builds practical understanding of IPv6 dynamic routing, routing protocol operation, neighbor verification, routing table analysis, and connectivity troubleshooting for the CCNA 200-301 certification.