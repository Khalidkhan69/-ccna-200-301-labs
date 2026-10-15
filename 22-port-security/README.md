# Lab 22 — Port Security (Access Port)

## Overview

This lab demonstrates Cisco switch port security on an access port using Cisco Packet Tracer.

Port security helps control which devices can connect to a switch port by limiting the number of MAC addresses learned or permitted on that port. It can help prevent unauthorized devices from accessing the network.

## Objectives

- Understand the purpose of switch port security.
- Configure port security on a switch access port.
- Limit the number of MAC addresses allowed on a port.
- Understand port security violation modes.
- Verify port security settings and status using Cisco IOS commands.

## Lab File

- `port-security(access-port).pkt` — Cisco Packet Tracer lab file.

## Key Concepts

- **Port security:** A Layer 2 security feature that restricts which MAC addresses can use a switch port.
- **Access port:** A switch port configured to connect an end device, typically belonging to a single VLAN.
- **Secure MAC address:** A MAC address permitted by the port security configuration.
- **Maximum MAC addresses:** The maximum number of secure MAC addresses allowed on a port.
- **Violation modes:** Actions taken when an unauthorized MAC address violates the port security policy.
- **Sticky MAC learning:** A feature that allows dynamically learned MAC addresses to be added to the running configuration.

## Verification Commands

Use the following commands on the switch to inspect port security configuration and operation.

### 1. Display port security status

```text
show port-security
```

Displays port security status and violation counters for switch interfaces.

### 2. Check a specific interface

```text
show port-security interface fa0/1
```

Displays port security settings and status for FastEthernet 0/1. Replace `fa0/1` with the interface configured in your topology.

### 3. Display secure MAC addresses

```text
show port-security address
```

Displays secure MAC addresses configured or learned on the switch.

### 4. Display interface configuration

```text
show running-config
```

Displays the active switch configuration, including configured port security commands.

### 5. Check interface status

```text
show interfaces status
```

Displays the status of switch interfaces and can help identify ports that are disabled or not connected.

## Expected Results

- Port security is enabled on the configured access port.
- The interface enforces the configured maximum number of secure MAC addresses.
- Secure MAC addresses are displayed when they have been configured or learned.
- Port security violations are recorded when configured security restrictions are breached.
- The interface responds according to its configured violation mode.

Actual results depend on the switch model, interface configuration, connected devices, and port security settings in the Packet Tracer file.

## Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- Ethernet switching
- MAC address security
- Switch access ports
- Port security violation modes

## Learning Outcome

This lab builds practical understanding of switch port security, MAC address restrictions, violation handling, and verification commands for the CCNA 200-301 certification.