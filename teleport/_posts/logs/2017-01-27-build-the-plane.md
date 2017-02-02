---
layout: post
categories: teleport logs
title: Build the plane
---
Having [already decided](/teleport/logs/plane-design) on the airframe we'll be using, the next step is to test it. However, the large plane that I ordered is going to take close to a month to arrive. In the mean time, I'll be running smaller form test (using ~1m wingspan foamies) to make sure that our fundamental assumptions are valid.

After all, I don't want the large 2m wingspan MTD plane to be my first attempt at such a test; a crash landing would mean another month of waiting!

## The smaller test
I ordered a couple of the [AXN Clouds Fly](https://hobbyking.com/en_us/floater-jet-epo-arf.html) floater, which arrived next day. This is smaller (just 1.1m wingspan) with a much lower wing area (remember that a proportionally sized 2m wing has 4 times the wing area of a 1m wing, not double). Still, the goal with this plane is a simple one: **run an autonomous flight as far as we possibly can**.

## Build
The foamie I ordered was just the body &mdash; it did not include any electronics, so I had to plug in the:

- Radio receiver
- Motor, electronic speed controller
- Autopilot (APM 2.8)
- Battery
- Servos (for control surfaces: ailerons, rudder and elevator)

The setup is pretty involved, and took me a good 5 hours to complete. 

Before:

![Unpacked](/assets/projects/teleport/axn-unpacked.png)

Here's a pic of the baby with everything installed (forgive the grainy mess, it'll be explained shortly):
![AXN grainy mess](/assets/projects/teleport/axn-grainy-mess.png)

For detailed build steps, I followed [this guide](http://beta.ivc.no/wiki/index.php/AXN_Clouds_Fly_Setup)

Once the build was complete, it was time for a maiden flight

## The maiden flight
For this first flight, I used a 2200 mAh Hobbyking battery, though I did plan to replace it with LiIon 3400 mAh batteries that have roughly double the energy density.

So I went to a nearby field, and took it out for a spin:
<iframe width="560" height="315" src="https://www.youtube.com/embed/M49BoK_RGzU" frameborder="0" allowfullscreen></iframe>

*Note*: The video won't be winning any Oscars, but it does capture a part of the crash in a few of the frames :/ I'll try and setup the camera so it's actually pointing at the plane in the next attempt. 

The flight went well initially, with the plane maintaining steady flight &mdash; though it did tend to pitch downwards. I tried trimming it up but that didn't really address the issue. It was still pitching down. I also noticed the controls had too much authority, so I changed the weight of the controls from my transmitter.

In the end, I was able to get it to fly in a semi-stable state but it did not gain much altitude. When I applied elevator, it would pitch up suddenly, then pitch down after I let go &mdash; in a see-saw fashion.

Eventually, the plane crashed in a tree &mdash; too high for me to retrieve:

![Stuck in Tree](/assets/projects/teleport/axn-stuck-tree.png)

I hadn't had much practice flying fixed wing craft so maybe I just didn't know what I was doing. It's a tertiary point though &mdash; the mission does not (and should not) depend on my ability to fly the plane.

I've now revised [the plan](/teleport) to include Autonomous flights only and not manual ones. This also saves me the trouble of figuring out how to get radio communication working over long distances.

## Lessons learned

- Don't learn to fly a plane with a real plane. Use a simulator to get the hang of things first, or just use an autopilot with waypoints configured
- The plane has to be able to gain altitude quicker
  - Increase propeller size for more power
  - Reduce the weight of the plane (use smaller battery pack, autopilot)

## Next steps
I'll run another test with the spare body that I have.

The changes I'll make:
- Use a larger prop to provide more power (I'll use a 6 inch prop instead of the 5 inch stock) resulting in quicker climbs. Reducing the weight will also help, since lower wing loading means faster climbs too.
- Add GPS and use waypoint or loiter flights (in loiter flight, the plane just flys around in circles at a fix altitude). I'll try and use a smaller autopilot since the APM is pretty big.
