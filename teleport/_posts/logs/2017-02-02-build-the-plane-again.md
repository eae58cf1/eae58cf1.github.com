---
layout: post
categories: teleport logs
title: Build the plane again
---
After the [first failed attempt](/teleport/logs/build-the-plane), I was able to retrieve the plane from the tree (using a rope and a bag of sand to pull the branch down):

![Plane retrieved from crash site](/assets/projects/teleport/axn-after-crash.png)

The plane body was mostly in tact, so I'll be using the same frame. I'll be making the changes we discussed after the last attempt, namely:
- ✅ Increase propeller size to 6 inches (from 5 inches previously)
- ✅ Reduce weight of the plane by using a smaller battery pack
- ✅ Use autopilot from the get-go. No manual flying

Also, some minor things to remember to do (based on the state of the retrieved plane):
- ✅ Make sure that the ESC is configured with a voltage cut-off. The motor was running even after the plane crashed into the tree, and continued to run until the 3-cell LiPo battery I was using was drained to 1.2V across all 3 cells! Luckily, I was able to [charge it back](https://www.rcgroups.com/forums/showthread.php?1072324-(HOW-TO)-Recovering-over-discharged-lipos). I got this done, after finding [this gem of a video](https://www.youtube.com/watch?v=E6epG5E8gAQ) that showed the calibration process, with complete list of options [here](https://dronebuildersblog.wordpress.com/2016/01/10/emax-blheli-brushless-esc-programming/#ep).
- ✅ Put lock-tight on the bullet prop adapter to prevent it from flying off. I lost mine somewhere in the woods.
- ✅ Properly secure the servos inside the fuselage (for elevator and rudder). Noticed that these were loose when inspecting the plane post-crash.

Onwards&hellip;

## The Lithium Ion battery pack
I'm creating a custom battery pack with a higher energy density than the Lithium Polymer batteries I previously used. This battery pack would pack more punch, at a lower weight (almost half). Take a look:

| LiPoly battery |                                         |
|:---------------|-----------------------------------------|
| Capacity       | 2.2Ah * 3S = 2.2Ah * 3 * 3.7 = 24.42 Wh |
| Weight         | 190 g                                   |
| Energy Density | Capacity / Weight = 128 Wh/kg           |

| LiIon          |                                          |
|:---------------|------------------------------------------|
| Capacity       | 3.4 Ah * 3S = 3.4Ah * 3 * 3.7 = 37.74 Wh |
| Weight         | 138 g                                    |
| Energy Density | 273 Wh/kg                                |

There you go &hellip; our LiIon pack has **2.13X more energy density** than the previous LiPo pack! The only downside to consider is that the discharge rating for LiIon is only ~2C (vs. ~30C for LiPo). This basically puts a limit on how fast you can discharge the cell, but if you wire these cells in parallel you can get more than enough current output for a simple glider.

I used 3.7V in both cases, but that's only true in average. Lipo batteries typically have a range from 3.2V - 4.2V / cell, with the average being 3.7V. Li-Ion batteries operate in a more stable 3.7V and then degrades quickly after that. You can see the Li-Ion discharge curve below:

![Lithium Ion discharge curve](/assets/projects/teleport/li-ion-discharge-curve.jpg)

For this example, I'll be using just one cell, so I'll need to monitor the power output and replace the cell with the LiPo if it's insufficient.

I've gone ahead and built the cell, include an XT-60 connector and a balance connector for charging:

![Custom built LiPo pack](/assets/projects/teleport/custom-lipo-cell.jpg)

I then did a power draw comparison between LiPo:
![LiPo power draw](/assets/projects/teleport/power-check-lipo.jpg)

&hellip; and Li Ion:
![Li Ion power draw](/assets/projects/teleport/power-check-liion.jpg)

The difference in current draw isn't huge (I = 2.1A for Lipo vs. 1.8A for Li-ion) so I'll just use the Li-Ion pack I made. 

## The Autopilot
I ordered the [Seriously Pro F3](http://seriouslypro.com/spracingf3) flight controller as a replacement for the bulky APM that I was previously using. I received that the next day (today) and spent a few solid hours going through the setup.

I had to solder the header pins in place and then start with the configuration of the board itself. The biggest time sink was getting the GPS unit to talk with the F3. I was using a Ublox NEO-6M (that was supposed to be supported by the F3) but it just wasn't flashing blue like it should. I'll try and wrap all those things up today and take it out for a test flight.

The only problem is that I lost the prop adapter collet that held the propeller in place after the crash &mdash; I ordered a replacement but that's going to take a week to arrive. I'll figure something out

![INAV GPS Not working](/assets/projects/teleport/inav-not-working-gps.png)

**UPDATE**: Spent the whole day trying to get the GPS to play nice with the autopilot and it did not work &mdash; which is strange since I was able to get it work for a brief minute before the whole thing just stopped working. Still, I won't waste more time on getting it to work &mdash; I've ordered the newer [Ublox NEO-8MN](https://www.u-blox.com/en/product/neo-m8-series) that they recommend and expect to get that in a few weeks. For now, I'll just fall back to the APM for further testing.

## Finishing touches
I've put everything together again, and now we're ready for the test flight:
![AXN - Take 2](/assets/projects/teleport/axn-take-2.jpg)

Unfortunately, it was insanely windy today (9th Feb) so I couldn't take it out for a spin. I'll plan to do that first thing tomorrow.

## Flight #2
Today I went out to fly the plane.

![Plane ready to roll](/assets/projects/teleport/axn-take-2-ready.jpg)

**First attempt**:
- I noticed that the ESC would continue beeping as soon as I plugged in the power. Once I moved the Throttle stick up, it would start the calibration procedure (which I didn't want). Turns out this behavior happened because it was receiving a high initial PWM value (>850) from the APM. I used my servo tester to provide an 800 value and then switched it back to the APM and it worked.

> Lesson: The calibration of the ESC seems off &mdash; get it fixed, or replace the cheap ESC with a more reliable one.

- After taking off, I noticed that it wouldn't bank left (when I applied left aileron). It could only turn right. Eventually, I brought it back down and checked the controls &mdash; they worked fine when the plane wasn't moving. Strange.
- I tried launching again. Same thing, but this time it didn't have such a light crash (the wings separated, though nothing broke). Upon closer inspection, I was shocked to find that I'd had the plane in Loiter mode &hellip; not Stabilize. What a stupid mistake! This is something I should've checked from the get-go.

> Lesson: Have a pre-flight checklist which includes things like checking the Flight mode in addition to the other tests I now do informally (e.g. control surfaces, center of gravity, etc.)

**Second attempt**:
- I put the plane back together (though it wasn't all that neat) and tried to fly it again. This time it took off, but I had to apply ALOT of up elevator just to keep it from nose-diving. This seemed familiar, and I was almost certain it was a center of gravity issue (something I hadn't re-checked after the first crash). Flight didn't last long before it crashed again. I checked and the battery was loose &mdash; I'd originally kept it in place by keeping it right between the foam edges at the nose of the plane, but it got dislodged after the first crash.

> Lesson: Secure the battery pack in place

In the end, the plane was in no shape to be flown again with any meaningful outcome. The wings had become dislodged, the CoG was random at best (because of the shifting battery pack) and the nose was rather crumpled. I decided to go back, fix it and try again tomorrow.

## Todo
Here's what I'll need to do ahead of the next flight:

- [ ] Secure battery in place
- [ ] Re-attach wings
- [ ] Fix nose
- [ ] Fix/Replace ESC
- [ ] Pre-flight checklist
