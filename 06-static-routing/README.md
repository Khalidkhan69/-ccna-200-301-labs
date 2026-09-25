# Lab 06: Static Routing

## Objective

Configure static routes so devices on different networks can communicate through multiple Cisco routers.

## Skills Practiced

- Configuring router interfaces
- Identifying remote destination networks
- Configuring static routes
- Selecting a next-hop router
- Understanding routing-table entries
- Testing end-to-end connectivity

## Static Route Syntax

```cisco
ip route <destination-network> <subnet-mask> <next-hop-ip>
```

Example:

```cisco
ip route 192.168.20.0 255.255.255.0 10.1.1.2
```

This sends traffic for `192.168.20.0/24` to the next-hop router at `10.1.1.2`.

## Verification Commands

```cisco
show ip route
show ip route static
show running-config | include ip route
show ip interface brief
```

## Connectivity Testing

```text
ping <destination-ip-address>
tracert <destination-ip-address>
```

## Lab File

- `static-routing.pkt`

## Tool

Cisco Packet Tracer