# Lab 05: Backup, Delete and Restore IOS Configuration

## Objective

Back up a Cisco router configuration to a TFTP server, delete the saved configuration and restore it from the server.

## Skills Practiced

- Configuring IP connectivity between a router and server
- Backing up a router configuration using TFTP
- Deleting the startup configuration
- Reloading the router
- Restoring a configuration from a TFTP server
- Saving and verifying the restored configuration

## Configuration Backup

```cisco
copy running-config tftp:
```

The router asks for:

- TFTP server IP address
- Destination filename

## Delete the Saved Configuration

```cisco
erase startup-config
reload
```

## Restore the Configuration

```cisco
copy tftp: running-config
copy running-config startup-config
```

The router asks for:

- TFTP server IP address
- Source filename

## Verification Commands

```cisco
show running-config
show startup-config
show ip interface brief
```

## Security Note

TFTP does not provide authentication or encryption. It should only be used in a controlled lab or trusted management network.

## Lab File

- `backup-delete-reinstall-ios-config.pkt`

## Tool

Cisco Packet Tracer