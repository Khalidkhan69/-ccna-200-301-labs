# Lab 08: Default Static Routing

## Objective

Configure default static routes so routers can forward packets for destinations that are not specifically listed in their routing tables.

## Skills Practiced

- Configuring a default static route
- Understanding the gateway of last resort
- Selecting a next-hop router
- Reading default-route entries in the routing table
- Testing end-to-end connectivity
- Troubleshooting missing routes

## Default Route Syntax

```cisco
ip route 0.0.0.0 0.0.0.0 <next-hop-ip>
```

Example:

```cisco
ip route 0.0.0.0 0.0.0.0 10.1.1.2
```

This command tells the router to forward packets to `10.1.1.2` when no more specific route matches the destination.

## Exit-Interface Method

```cisco
ip route 0.0.0.0 0.0.0.0 <exit-interface>
```

Example:

```cisco
ip route 0.0.0.0 0.0.0.0 gigabitEthernet 0/1
```

## Verification Commands

```cisco
show ip route
show ip route static
show running-config | include ip route
show ip interface brief
```

The default static route appears as:

```text
S* 0.0.0.0/0 via <next-hop-ip>
```

- `S` means static route.
- `*` means candidate default route.
- `0.0.0.0/0` represents all destinations not matched by a more specific route.

## Connectivity Testing

```text
ping <destination-ip-address>
tracert <destination-ip-address>
```

## Lab File

- `default-static-routing.pkt`

## Tool

Cisco Packet Tracer