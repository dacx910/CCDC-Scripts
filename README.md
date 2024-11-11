# One-liners
Here's a list of one-liners that I've found to discover certain things:


## Detect Established Shells
    ss -p | grep "ESTAB" | grep --invert "*" 
Detects basic meterpreter shells, will also output NetworkManager and other established connections
> *ss can be swapped for netstat
## Deleted & Running Processes

    lsof | grep "deleted"
   Will output all processes running while their file is deleted. Anything running as root should be closely inspected.
   
   Filtering for root processes:

	lsof -u root | grep "deleted"
