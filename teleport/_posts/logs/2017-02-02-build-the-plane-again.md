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
- Make sure that the ESC is configured with a voltage cut-off. The motor was running even after the plane crashed into the tree, and continued to run until the 3-cell LiPo battery I was using was drained to 1.2V across all 3 cells! Luckily, I was able to [charge it back](https://www.rcgroups.com/forums/showthread.php?1072324-(HOW-TO)-Recovering-over-discharged-lipos).
- Put lock-tight on the bullet prop adapter to prevent it from flying off. I lost mine somewhere in the woods.
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

For this example, I'll be using just one cell, so I'll need to monitor the power output and replace the cell with the LiPo if it's insufficient.

## The Autopilot
I ordered the [Seriously Pro F3](http://seriouslypro.com/spracingf3) flight controller as a replacement for the bulky APM that I was previously using. I received that the next day (today) and spent a few solid hours going through the setup.

I had to solder the header pins in place and then start with the configuration of the board itself. The biggest time sink was getting the GPS unit to talk with the F3. I was using a Ublox NEO-6M (that was supposed to be supported by the F3) but it just wasn't flashing blue like it should. I'll try and wrap all those things up today and take it out for a test flight.

The only problem is that I lost the prop adapter collet that held the propeller in place after the crash &mdash; I ordered a replacement but that's going to take a week to arrive. I'll figure something out.
