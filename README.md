# CCNA 200-301 Packet Tracer Labs

This repository documents my practical learning journey for the Cisco CCNA 200-301 certification. It contains Cisco Packet Tracer labs, configuration examples, and verification commands covering networking fundamentals, routing, switching, and network security.

## Labs

| Lab | Topic | Description |
|---|---|---|
| 01 | [Basic Router Configuration](./01-basic-router-configuration/) | Cisco IOS navigation, interface configuration, and configuration verification |
| 02 | [Router as a DHCP Server](./02-router-as-dhcp-server/) | DHCP exclusions, DHCP pools, gateway assignment, and automatic client addressing |
| 03 | [Telnet Configuration](./03-telnet-configuration/) | Remote CLI access using VTY lines and Telnet |
| 04 | [SSH Configuration](./04-ssh-configuration/) | Secure remote administration using SSH and local authentication |
| 05 | [Configuration Backup and Restore](./05-backup-delete-reinstall-ios-config/) | Back up, delete, and restore a Cisco IOS configuration using TFTP |
| 06 | [Static Routing](./06-static-routing/) | Configure manually defined routes between remote networks |
| 07 | [Floating Static Routing](./07-floating-static-routing/) | Configure a backup route using a higher administrative distance |
| 08 | [Default Static Routing](./08-default-static-routing/) | Forward unknown destinations through a gateway of last resort |
| 09 | [RIP Dynamic Routing](./09-rip-routing(dynamic)/) | Configure RIP, advertise connected networks, and verify dynamically learned routes |
| 10 | [EIGRP Dynamic Routing](./10-eigrp-routing(dynamic)/) | Configure EIGRP, advertise networks, and verify neighbors and dynamically learned routes |
| 11 | [OSPF Dynamic Routing](./11-ospf-routing(dynamic)/) | Configure OSPF, advertise networks, and verify neighbor relationships and learned routes |
| 12 | [Route Redistribution](./12-redistribution/) | Redistribute routes between OSPF and EIGRP and verify external routing information |
| 13 | [Numbered Standard ACL](./13-standard-acl(number)/) | Filter IPv4 traffic using numbered standard ACLs and source addresses |
| 14 | [Numbered Extended ACL](./14-extended-acl(number)/) | Filter traffic using protocols, source and destination addresses, and port numbers |
| 15 | [Named Standard ACL](./15-standard-acl(name)/) | Filter IPv4 traffic by source address using a descriptive ACL name |
| 16 | [Named Extended ACL](./16-extended-acl(name)/) | Filter traffic by protocol, addresses, and port numbers using a descriptive ACL name |
| 17 | [VLAN Access Ports and Trunking](./17-vlan(access-port+trunk-link)/) | Create VLANs, assign access ports, and configure IEEE 802.1Q trunk links between switches |
| 18 | [Inter-VLAN Routing Using Multilayer Switch](./18-inter-vlan-routing(mls)/) | Configure VLAN interfaces (SVIs) and enable Layer 3 routing on a multilayer switch |
| 19 | [Inter-VLAN Routing Using Router](./19-inter-vlan-routing(router)/) | Configure router subinterfaces and IEEE 802.1Q encapsulation for inter-VLAN routing |
| 20 | [VTP Configuration](./20-vtp/) | Configure VLAN Trunking Protocol (VTP), understand VTP modes and domains, and verify VLAN information across switches |
| 21 | [Per-VLAN Spanning Tree](./21-per-vlan-spanning-tree/) | Explore PVST+, root bridge election, spanning-tree port roles, and Layer 2 loop prevention |
| 22 | [Port Security (Access Port)](./22-port-security/) | Configure switch port security, restrict MAC addresses, and verify security settings and violation handling |
| 23 | [IPv6 Static and Default Routing](./23-ipv6-static+default-routing/) | Configure IPv6 static and default routes, verify routing table entries, and test IPv6 connectivity |

## Skills Practiced

### Networking Fundamentals
- Cisco IOS command-line interface
- IPv4 addressing and subnet masks
- IPv6 addressing and interface configuration
- Router and interface configuration
- Network connectivity testing
- Configuration verification and troubleshooting

### IP Services and Remote Access
- DHCP configuration and address assignment
- DHCP exclusions and address pools
- VTY line configuration
- Telnet and SSH remote access
- Local user authentication
- Configuration backup and recovery using TFTP

### Static and Dynamic Routing
- Static routing and next-hop selection
- Default routes and the gateway of last resort
- Floating static routes and administrative distance
- Route redundancy and failover
- Dynamic routing using RIP and RIPv2
- Dynamic routing using EIGRP
- EIGRP autonomous system configuration
- EIGRP neighbor and topology verification
- Dynamic routing using OSPF
- OSPF process ID and router ID configuration
- OSPF area configuration and neighbor verification
- Route redistribution between OSPF and EIGRP
- EIGRP seed metric configuration
- External route verification
- IPv6 static route configuration
- IPv6 default route configuration
- IPv6 routing table verification
- IPv6 connectivity testing and troubleshooting

### Access Control and Network Security
- Standard and extended IPv4 access control lists
- Numbered and named ACL configuration
- Source and destination address filtering
- Protocol and port-number filtering
- Inbound and outbound ACL application
- ACL placement and implicit deny
- Switch port security configuration
- Secure MAC address learning and restrictions
- Port security violation modes
- Port security status and MAC address verification
- Access-port security and unauthorized device prevention

### Switching and VLANs
- VLAN creation and naming
- Access-port and trunk-link configuration
- IEEE 802.1Q VLAN tagging
- VLAN traffic across multiple switches
- Inter-VLAN routing using a multilayer switch
- Switch virtual interfaces (SVIs)
- Layer 3 switching
- Router-on-a-stick configuration
- Router subinterfaces
- Network advertisement and wildcard mask configuration
- VLAN Trunking Protocol (VTP)
- VTP domains and operating modes
- VTP server, client, and transparent modes
- VTP advertisements and VLAN information management
- Spanning Tree Protocol (STP)
- Per-VLAN Spanning Tree Plus (PVST+)
- Root bridge election and spanning-tree port roles
- Layer 2 loop prevention
- Spanning-tree verification and troubleshooting

## Tools

- Cisco Packet Tracer
- Cisco IOS CLI
- Git and GitHub
- TFTP server

## Progress

This repository will continue to grow as I complete additional CCNA labs, including:

- EtherChannel
- Network Address Translation (NAT)
- IPsec VPNs and GRE tunnels
- Additional switching, routing, IPv6, and network security labs

## Author

**Khalid Ikram**

Aspiring network and cybersecurity professional