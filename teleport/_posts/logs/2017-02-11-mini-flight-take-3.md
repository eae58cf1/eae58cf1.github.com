---
layout: post
categories: teleport logs
title: Scaled flight &mdash; Take 3
---
Here's what we learned from [the last flight](/teleport/logs/build-the-plane-again/):

- ✅ Secure battery in place
- ✅ Re-attach wings
- ✅ Fix nose
- ✅ Fix/Replace ESC
- ✅ Pre-flight checklist

## Pre-flight checklist
From today onwards, before every flight, I'll be following the below sequence:

- Calibrate APM (Compass &amp; Accelerometer)
- Check battery level. Charge if necessary
- Check center of gravity. It should be about 1/3rd of the chord behind the front edge of the wing.
- Balance the propeller
- Check control surfaces
	- Right pitch on transmitter should move **right aileron up** and left aileron down. Left pitch should do the opposite
	- Check centering on control surfaces when the transmitter controls are neutral. They should be flush with the body
- Switch to Stabilize mode. Move the plane across all axes and check that the compensation it makes is consistent with what you'd expect (if you roll left, expect it to attempt to counteract that roll by rolling right).
- Check Flight mode on Transmitter
- Check for GPS lock (flashing blue LED on the GPS unit) 

## Additional mods
I made a few more departures from previous attempts:

- Removed the APM case. There just wasn't enough space to keep the whole thing in there, so I just removed the case. Will monitor the vibration levels on the APM to see if this is OK. For now, I just added some vibration absorbing tape under the APM board where it attaches to the plane.
- Added a power switch. Removing the battery connector from the APM power module is just a pain, and it moves the APM board just ever so slightly each time. I just replaced the whole ordeal with a push switch. Now it's just a flick of a switch to power on/off the plane.
- Did not apply lock-tight to the propeller. I couldn't screw the collet adapter onto the propeller holder properly, so I stopped applying it. Now I just make extra sure that it's nice and tight.
- Put a sheet of aluminium foil under the APM to help reduce the interference with the onboard magnetometer (compass) from the power wires just underneath it. If that doesn't work, I'll wire up the external magentometer on the GPS (Hadn't done that yet because I don't have the DF13 connector that the APM uses). 

## Flight
I made a video of the flight attempt but my crappy camera recorded a corrupt file. Here's what happened:

![AXN - Take 3 - ready](/assets/projects/teleport/axn-take-3-ready.png)

It was snowing today but I decided to take it out anyway. This time, I made sure to follow the pre-flight checklist and the take off was really smooth. There was just one issue &mdash; I couldn't get much lift. Despite applying full elevator the plane was unable to stay up in the air for long. It was stable, so it wasn't a center of gravity problem &mdash; it just didn't gain altitude.

After a few attempts, all ending up with the plane gliding down to the ground (despite full throttle and max elevator), I stopped trying. I went back and checked on the weight (something I hadn't done earlier):

![Overweight AXN](/assets/projects/teleport/axn-take-3-overweight.png)

There you go. The recommended weight is between 550 - 570g and my plane weighed in at 693g! That's 123 grams over the manufacturer limit, no wonder.

A heavier plane needs to move faster in order to stay in the air. The faster speed would result in more lift, but it comes at the cost of greater drag. In order to overcome this increased drag, we need to have more thrust.

I now have two options:
- Reduce the weight
- Increase the thrust (in order to overcome the extra drag that comes with the added weight). I may also need to launch it at a higher speed in order to achieve the minimum lift (e.g. using a catapult)

> Lesson learned: Shed some weight or increase the thrust (with a faster/torque-ier motor, or a larger prop)

