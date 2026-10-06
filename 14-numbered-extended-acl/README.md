# Lab 14 - Numbered Extended ACL

## Overview

This lab demonstrates how to configure a numbered extended Access Control List (ACL). Extended ACLs can filter traffic using protocols, source addresses, destination addresses and port numbers.

## Objectives

- Configure a numbered extended ACL
- Filter traffic by protocol
- Filter traffic by source and destination addresses
- Filter TCP or UDP traffic by port number
- Apply an ACL inbound or outbound
- Verify ACL operation and test connectivity

## Extended ACL Numbers

Extended numbered ACLs commonly use these ranges:

```text
100-199
2000-2699
```

## Basic Syntax

```cisco
access-list <acl-number> permit|deny <protocol> <source> <source-wildcard> <destination> <destination-wildcard>
```

Apply the ACL to an interface:

```cisco
interface <interface-name>
ip access-group <acl-number> in|out
```

## Example Configuration

Block HTTP traffic from `192.168.10.0/24` to a server:

```cisco
access-list 100 deny tcp 192.168.10.0 0.0.0.255 host 192.168.30.10 eq 80
access-list 100 permit ip any any

interface gigabitEthernet 0/0
ip access-group 100 in
```

## Important Notes

- Extended ACLs check protocols, source addresses, destination addresses and port numbers.
- ACL statements are processed from top to bottom.
- The first matching statement is applied.
- Every ACL has an implicit `deny any` at the end.
- Extended ACLs are generally placed close to the source.

## Verification Commands

```cisco
show access-lists
show ip access-lists
show ip interface
show running-config
ping <destination-ip-address>
```

## Tool Used

- Cisco Packet Tracer

## Lab File

- `numbered-extended-acl.pkt`