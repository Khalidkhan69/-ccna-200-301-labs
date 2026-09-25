# Lab 07: Floating Static Routing

## Objective

Configure a floating static route that provides a backup path when the primary route becomes unavailable.

## Skills Practiced

- Configuring primary and backup routes
- Understanding administrative distance
- Assigning a higher administrative distance to a backup route
- Creating route redundancy
- Testing failover and recovery
- Verifying routing-table changes

## Configuration Outline

Primary static route:

```cisco
ip route <destination-network> <subnet-mask> <primary-next-hop>
```

Floating backup route:

```cisco
ip route <destination-network> <subnet-mask> <backup-next-hop> <administrative-distance>
```

Example:

```cisco
ip route 192.168.20.0 255.255.255.0 10.1.1.2
ip route 192.168.20.0 255.255.255.0 10.2.2.2 10
```

The primary static route uses the default administrative distance of `1`. The backup route uses administrative distance `10`, so it becomes active only when the primary route is unavailable.

## Verification Commands

```cisco
show ip route
show ip route static
show running-config | include ip route
```

## Failover Test

1. Verify that traffic uses the primary route.
2. Shut down the primary connection.
3. Check that the floating static route enters the routing table.
4. Test connectivity through the backup path.
5. Restore the primary connection and verify route recovery.

## Lab File

- `floating-static-routing.pkt`

## Tool

Cisco Packet Tracer