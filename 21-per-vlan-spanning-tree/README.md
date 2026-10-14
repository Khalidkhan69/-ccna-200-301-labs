# Lab 21 — Per-VLAN Spanning Tree (PVST+)

## Overview

This lab demonstrates Per-VLAN Spanning Tree Plus (PVST+), a Cisco spanning-tree implementation that maintains a separate spanning-tree instance for each VLAN.

PVST+ helps prevent Layer 2 switching loops while allowing different VLANs to use different root bridges and spanning-tree paths.

## Objectives

- Understand the purpose of Spanning Tree Protocol (STP).
- Understand how PVST+ operates on a per-VLAN basis.
- Identify root bridges and spanning-tree port roles.
- Verify spanning-tree operation using Cisco IOS commands.

## Lab File

- `per-vlan-spanning-tree.pkt` — Cisco Packet Tracer lab file.

## Key Concepts

- **Layer 2 loops:** Can cause broadcast storms, duplicate frames, and MAC address table instability.
- **Root bridge:** The switch elected as the reference point for a spanning-tree instance.
- **Port roles:** Root, designated, and alternate roles help determine which paths forward traffic.
- **Per-VLAN operation:** Different VLANs can have different root bridges and forwarding paths.

## Verification Commands

Use the following commands on the switches to inspect the spanning-tree configuration and operation.

### 1. Display spanning-tree information

```text
show spanning-tree
```

Displays spanning-tree information for the default or current VLAN context.

### 2. Check a specific VLAN

```text
show spanning-tree vlan 10
```

Displays spanning-tree information for VLAN 10. Replace `10` with a VLAN ID configured in your topology.

### 3. Display VLAN information

```text
show vlan brief
```

Displays VLANs and their access-port assignments.

### 4. Verify trunk links

```text
show interfaces trunk
```

Displays operational trunk ports and their trunking information.

### 5. Check the switch configuration

```text
show running-config
```

Displays the active configuration, which can help verify spanning-tree settings.

## Expected Results

- Spanning-tree information is available for configured VLANs.
- Each spanning-tree instance has an elected root bridge.
- Redundant Layer 2 paths are managed to prevent switching loops.
- Different VLANs may have different root bridges and forwarding paths, depending on the configuration.

Actual results depend on the topology and switch configuration in the Packet Tracer file.

## Technologies

- Cisco Packet Tracer
- VLANs
- Spanning Tree Protocol (STP)
- Per-VLAN Spanning Tree Plus (PVST+)
- Layer 2 switching

## Learning Outcome

This lab builds practical understanding of Layer 2 loop prevention, root bridge election, spanning-tree port roles, and per-VLAN spanning-tree verification for the CCNA 200-301 certification.
