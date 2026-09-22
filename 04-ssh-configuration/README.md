# Lab 04: SSH Configuration

## Objective

Configure secure remote access to a Cisco router using SSH and local user authentication.

## Skills Practiced

- Configuring a hostname and domain name
- Creating a local user account
- Generating RSA encryption keys
- Enabling SSH version 2
- Configuring VTY lines for SSH
- Testing secure remote access

## Configuration Outline

```cisco
hostname R1
ip domain-name lab.local
username admin secret <password>
crypto key generate rsa
ip ssh version 2

line vty 0 4
 login local
 transport input ssh
```

## Testing

```text
ssh -l admin <router-ip-address>
```

## Verification Commands

```cisco
show ip ssh
show running-config | section line vty
show users
```

## Lab File

- `lab04-ssh-configuration.pkt`

## Tool

Cisco Packet Tracer