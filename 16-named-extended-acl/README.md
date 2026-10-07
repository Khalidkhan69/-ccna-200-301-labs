# Lab 16: Named Extended ACL

## Overview

This lab demonstrates how to configure a named extended IPv4 Access Control List on a Cisco router. An extended ACL can filter traffic using protocols, source addresses, destination addresses and port numbers.

## Objectives

- Create a named extended ACL
- Filter traffic by protocol
- Match source and destination IPv4 addresses
- Filter TCP and UDP traffic using port numbers
- Apply the ACL to a router interface
- Verify ACL operation and connectivity

## Key Concepts

- Named extended ACLs use descriptive names instead of numbers.
- Extended ACLs can examine protocols, source addresses, destination addresses and ports.
- Extended ACLs should normally be placed close to the traffic source.
- ACL entries are processed from top to bottom.
- The first matching rule is applied.
- Every ACL has an implicit `deny ip any any` at the end.

## Example Configuration

```cisco
Router(config)# ip access-list extended BLOCK_HTTP
Router(config-ext-nacl)# deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.10 eq 80
Router(config-ext-nacl)# permit ip any any
Router(config-ext-nacl)# exit

Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip access-group BLOCK_HTTP in