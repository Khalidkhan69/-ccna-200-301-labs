# Lab 13 - Numbered Standard ACL

## Overview

This lab demonstrates how to configure a numbered standard Access Control List (ACL) on a Cisco router. A standard ACL filters traffic using only the source IPv4 address.

## Objectives

- Configure a numbered standard ACL
- Permit or deny traffic based on source IP addresses
- Use wildcard masks in ACL statements
- Apply an ACL inbound or outbound on an interface
- Understand the implicit deny rule
- Verify ACL operation and test connectivity

## Standard ACL Numbers

Standard numbered ACLs commonly use these ranges:

```text
1-99
1300-1999
```

## Basic Syntax

```cisco
access-list <acl-number> permit|deny <source-address> <wildcard-mask>
```

Apply the ACL to an interface:

```cisco
interface <interface-name>
ip access-group <acl-number> in|out
```

## Example Configuration

Permit the `192.168.10.0/24` network:

```cisco
access-list 10 permit 192.168.10.0 0.0.0.255

interface gigabitEthernet 0/1
ip access-group 10 out
```

Permit all remaining traffic when required:

```cisco
access-list 10 permit any
```

## Important Notes

- A standard ACL checks only the source IPv4 address.
- ACL statements are processed from top to bottom.
- The first matching statement is applied.
- Every ACL has an implicit `deny any` at the end.
- Standard ACLs are generally placed close to the destination.

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

- `numbered-standard-acl.pkt`