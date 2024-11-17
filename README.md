# CCDC Scripts

This is a collection of scripts and other things for use in CCDC, but they'll also work for other cyberdefense purposes.

## One-Liners

Here's a list of one-liners that I've found to discover certain things:

### Listening Processes

```
ss -tulpn
```

> ss can be swapped for the netstat command

Doesn't often return lots of results, but can be filtered out using grep.

Notable fields include UNCONN/LISTEN and udp/tcp.

### Detect Established Shells

    ss -p | grep "ESTAB" | grep --invert "*" 

> ss can be swapped for netstat

Detects basic meterpreter shells, will also output NetworkManager and other established connections.

Note that other forms of shells (like netcat listeners) will *not* show up since they're LISTENING connections.

### Deleted & Running Processes

     lsof -u root | grep "deleted"

lsof can return thousands of results (even when filtering out for deleted files), so this will filter out for processes running as root.

root should not have any files running as deleted, any results are at minimum highly suspect.
