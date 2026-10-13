# Lab 20: VLAN Trunking Protocol (VTP) Configuration

## Overview

This lab focuses on the configuration and verification of the **VLAN Trunking Protocol (VTP)** in a Cisco switching environment using Cisco Packet Tracer.

VTP is a Cisco proprietary Layer 2 protocol that allows switches in the same VTP domain to advertise and synchronize VLAN information, depending on their VTP configuration and version.

## Objectives

- Understand the purpose and operation of VTP.
- Understand VTP domains and operating modes.
- Learn the differences between VTP server, client, and transparent modes.
- Configure VTP settings on Cisco switches.
- Understand the relationship between trunk links and VTP advertisements.
- Verify VTP status and VLAN information using Cisco IOS commands.

## Topics Covered

- VLAN Trunking Protocol (VTP)
- VTP domain configuration
- VTP server mode
- VTP client mode
- VTP transparent mode
- VLAN information advertisement and synchronization
- Switch-to-switch trunk links
- VLAN verification and troubleshooting

## Configuration Commands

The following are example commands for configuring VTP on a Cisco switch. Use the appropriate domain name, operating mode, and VTP version for your actual Packet Tracer topology.

### 1. Enter Global Configuration Mode

```text
enable
configure terminal
```

### 2. Configure the VTP Domain

```text
vtp domain CCNA
```

The domain name must match across participating switches for them to exchange VTP information.

### 3. Configure the VTP Mode

For a VTP server:

```text
vtp mode server
```

For a VTP client:

```text
vtp mode client
```

For a VTP transparent switch:

```text
vtp mode transparent
```

Configure only the mode appropriate for each switch in your topology.

### 4. Configure a Trunk Link

Example interface configuration:

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

Use the correct interface identifier for your topology. Trunk links are commonly used to carry traffic and VTP advertisements between switches.

### 5. Verify the Configuration

```text
show vtp status
show vlan brief
show interfaces trunk
```

These commands help verify VTP settings, VLAN information, and trunk status.

## VTP Operating Modes

| Mode | Description |
|---|---|
| Server | Can create, modify, and delete VLANs and advertise VLAN information. |
| Client | Learns and synchronizes VLAN information from VTP advertisements; cannot normally create or modify VLANs locally. |
| Transparent | Maintains VLAN information locally and forwards VTP advertisements according to the VTP version and configuration. |

## Verification and Testing

After configuring the switches:

1. Verify that participating switches use the intended VTP domain.
2. Check each switch's VTP operating mode.
3. Confirm that the required trunk links are operational.
4. Create a test VLAN on the VTP server if required by the lab.
5. Check whether the VLAN appears on the other switches as expected.
6. Use `show vlan brief` and `show vtp status` to investigate any discrepancies.

## Expected Outcome

After completing this lab, you should be able to explain VTP operation, configure VTP modes and domains, verify VLAN information, and troubleshoot basic VTP synchronization issues.

## Lab File

**Packet Tracer file:** `vtp.pkt`

Open `vtp.pkt` in Cisco Packet Tracer to inspect the topology and perform the lab configurations.

## Skills Practiced

- Cisco IOS CLI
- VLAN management
- VTP configuration and verification
- Switch operating modes
- Trunk configuration
- Inter-switch VLAN information synchronization
- Network troubleshooting

