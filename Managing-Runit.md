# Introduction
[runit](http://smarden.org/runit/) is the default init for Venom Linux. runit is a cross-platform Unix init scheme with service supervision, a replacement for sysvinit, and other init schemes.

## runit directories
- `/var/service` - Linked to current runlevel, all services in this directory considered active.
- `/etc/sv` - Directory contain all services in Venom Linux.
- `/etc/runit/runsvdir` - Directory contains runlevel.

## Usage
To start a service:
```
# sv up <service name>
```

To stop a service:
```
# sv down <service name>
```

To restart a service:
```
# sv restart <service name>
```

To get current status of a service:
```
# sv status <service name>
```

To get current status of all enabled services:
```
# sv status /var/service/*
```

To enable a service:
```
# ln -s /etc/sv/<service name> /var/service
```

To disable a service:
```
# rm /var/service/<service name>
```

To keep a enabled service from starting automatically at boot, create a file named down in the service directory.
```
# touch /etc/sv/<service name>/down
```