---
layout: page
title: Zero days
---
Just finished watching the movie Zero Days, which talks about the joint US-Israeli cyber attack on Iranian nuclear facilities.

- There's a rush to arm in cyber offensive security. The attempt on Iran seems to have backfired, with Iran themselves launching their own offensive.
- The core issue is the reliance of any core system on vendors lower in the software stack (e.g. Centrifuge motors built by certain vendors, Siemens PLCs running on Windows)
- Weak players will seek laws and reconciliation; the strong (and talented) don't care.
- There was a greater plan to take out the core infrastructure in Iran in the event of an attack on Iran (roads, banks, military equipment so it doesn't attack invading targets, etc.). Of course, this could also have been made up in an attempt to psychologically cause the Iranians to fold but who really wants to find out?
- In the end, Iran gave up. They announced an Iran de-weaponization of their nuclear arsenal.

# Solution
Is there one? The nuclear sites were air-gapped (they are not connected to the internet), but they were *still* infiltrated via 2 vectors:
- Vendors/contractors, 
- Spies / assets on location

Makes you wonder if there's actually any way that you can fix this issue at all? 

You can't rebuild everything from scratch (Operating System, hardware, drivers to connect the two, network to connect this with all the other computers, protocols for Internet communication). The attackers realize that you have to place your trust in some segment of the stack &mdash; and that's where the exploit will lie.
