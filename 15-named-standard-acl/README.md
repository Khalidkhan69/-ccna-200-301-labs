# Lab 15: Named Standard ACL

## Overview

This lab demonstrates how to configure a named standard IPv4 Access Control List on a Cisco router. A standard ACL filters traffic using only the source IPv4 address.

## Objectives

- Create a named standard ACL
- Permit or deny traffic based on source addresses
- Apply the ACL to a router interface
- Understand inbound and outbound ACL directions
- Verify ACL configuration and matches
- Test network connectivity

## Key Concepts

- Named standard ACLs use descriptive names instead of numbers.
- Standard ACLs examine only the source IPv4 address.
- Standard ACLs should normally be placed close to the destination.
- ACL entries are processed from top to bottom.
- The first matching rule is applied.
- Every ACL has an implicit `deny any` at the end.

## Example Configuration

```cisco
Router(config)# ip access-list standard BLOCK_LAN
Router(config-std-nacl)# deny 192.168.10.0 0.0.0.255
Router(config-std-nacl)# permit any
Router(config-std-nacl)# exit

Router(config)# interface gigabitEthernet 0/1
Router(config-if)# ip access-group BLOCK_LAN out