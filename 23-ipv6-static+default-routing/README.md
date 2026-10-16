# Lab 23 — IPv6 Static and Default Routing

## Overview

This lab demonstrates how to configure IPv6 static routes and default routes on Cisco routers using Cisco Packet Tracer.

IPv6 static routing allows administrators to manually define paths to destination networks, while an IPv6 default route provides a route for destinations that do not have a more specific matching entry in the routing table.

## Objectives

- Understand IPv6 static routing.
- Configure IPv6 addresses on router interfaces.
- Configure IPv6 static routes between networks.
- Configure an IPv6 default route.
- Verify IPv6 routing table entries.
- Test end-to-end IPv6 connectivity.

## Lab File

- Cisco Packet Tracer `.pkt` file included in this folder.

## Key Concepts

- **IPv6 addressing:** Uses 128-bit addresses to identify interfaces and networks.
- **Static routing:** Manually defines a path to a destination IPv6 network.
- **Default routing:** Provides a route for destinations without a more specific matching route.
- **Next-hop address:** Identifies the next router toward the destination.
- **IPv6 routing table:** Stores routes used to forward IPv6 packets.

## Verification Commands

### 1. Display IPv6 interfaces

```text
show ipv6 interface brief
```

Displays IPv6 addresses and the status of router interfaces.

### 2. Display the IPv6 routing table

```text
show ipv6 route
```

Displays IPv6 routes, including static and default routes.

### 3. Display the running configuration

```text
show running-config
```

Displays the active router configuration.

### 4. Test IPv6 connectivity

```text
ping ipv6-address
```

Replace `ipv6-address` with the IPv6 address of the destination device.

## Expected Results

- Router interfaces have the correct IPv6 addresses.
- Static routes appear in the IPv6 routing table when correctly configured and usable.
- The default route directs traffic toward the configured next hop.
- Devices in remote IPv6 networks can communicate when routing and return paths are configured correctly.

Actual results depend on the topology and configuration in the Packet Tracer file.

## Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv6 addressing
- IPv6 static routing
- IPv6 default routing
- ICMPv6 connectivity testing

## Learning Outcome

This lab develops practical understanding of IPv6 addressing, static route configuration, default route selection, routing table verification, and IPv6 connectivity troubleshooting for the CCNA 200-301 certification.