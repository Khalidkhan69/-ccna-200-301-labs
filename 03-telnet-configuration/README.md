# Lab 03: Telnet Configuration

## Objective

Configure remote access to a Cisco router using Telnet and VTY lines.

## Skills Practiced

- Configuring VTY lines
- Setting a VTY password
- Enabling Telnet access
- Testing remote CLI access
- Viewing active remote sessions

## Configuration Outline

```cisco
line vty 0 4
 password <password>
 login
 transport input telnet
```

## Testing

```text
telnet <router-ip-address>
```

## Verification Commands

```cisco
show running-config | section line vty
show users
```

## Security Note

Telnet sends usernames, passwords and commands without encryption. It should only be used for learning in a lab environment. SSH is recommended for secure remote administration.

## Lab File

- `lab03-telnet-configuration.pkt`

## Tool

Cisco Packet Tracer