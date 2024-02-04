# SuperSNAWorld
 AS400 toolkit for SSW

MACHLIST (RPGLE) - Should be a program that displays the status of all machines enrolled in SSW. There needs to be a helper program that polls all SDLC lines and determines if they're ACTIVE or RCNDL; the helper program should call another program that either makes modifications to the status DB or writes to a data queue. MACHLIST will periodically refresh either automatically or when new data is in the data queue. Let's try to implement a data queue so I can learn something new. I should also use "virtual PFs" (I forget what they're called atm) to allow for search features.

ENROLLSYS (CL/RPGLE) - Helper program for administering systems and adding to DB. Part 1 is a CL stub that takes in the hostname of the new system to be added (and VMAC IDs?). Part 2 is an RPGLE program that writes the new machine to the DB. Part 3 should be a CL program that adds the SDLC line automatically based on the given hostname and VMAC parameters in part 1.

DELSYS (CL/RPGLE) - Inverse of ENROLLSYS, likely a 3-part program in CL/RPGLE/CL.