# Lab 02: Router as a DHCP Server

## Objective

Configure a Cisco router to automatically provide IP addressing information to network clients.

## Skills Practiced

- Configuring a router interface
- Excluding reserved IP addresses
- Creating a DHCP pool
- Configuring the network and subnet mask
- Providing a default gateway to clients
- Obtaining IP addresses automatically
- Testing network connectivity

## Example DHCP Configuration

```cisco
ip dhcp excluded-address 192.168.10.1 192.168.10.10

ip dhcp pool LAN
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
```

## Verification Commands

```cisco
show ip dhcp binding
show ip dhcp pool
show ip interface brief
```

## Lab File

- `lab02-router-as-a-dhcp-server.pkt`

## Tool

Cisco Packet Tracer