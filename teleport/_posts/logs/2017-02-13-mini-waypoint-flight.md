---
layout: post
categories: teleport logs
---

After the APM burned out following my [successful flight](/teleport/logs/mini-flight-take-4) yesterday, I swapped it out for another APM I had lying around. That didn't work unfortunately (I'd bought it off eBay a while ago, and it was crap). I ordered another one, and now waiting till it arrives (expected delivery on Wednesday).

That's what sucks about hardware projects like this &mdash; whereas a software project is always waiting on you, here you're waiting on part deliveries (I'm also still waiting on the full-sized model too, which got pushed back a month; looks like the Chinese factory is waiting to do a million-product run in order for the economics to work out).

Alas, wait we shall until Wednesday for the waypoint flight.

## Received the GPS unit for the F3
I just received the NEO-8MN GPS unit [I was waiting on](/teleport/logs/build-the-plane-again/#the-autopilot) in order to get the F3 flight controller (from Seriously Pro) working in autonomous mode. Unfortunately, after extensive testing it was clear that the GPS unit I received was a cheap clone, and did **not** work (I'd ordered it from a Chinese store online, so I'm not exactly shocked).

I've ordered a replacement, but that does set me back while I wait for it to come in. Still no autopilot, so we can't go ahead.

## APM replacement is in
Finally received my APM and set it up. This worked well, and I also discovered why the previous one didn't. The old one failed in the compass calibration process; upon further inspection, I discovered that there was [a jumper that's used to select the compass](https://www.unmannedtechshop.co.uk/ardupilot-apm-2-8-flight-controller-board/). Once I set that, it worked fine.

![APM jumper](/assets/projects/teleport/apm-internal-compass.jpg)

So I got everything in place, and took it out for a spin &mdash; despite ridiculously strong wind conditions (~45kph winds):

![AXN ready to go](/assets/projects/teleport/take-5-ready-to-go.png)

I setup the plane with some waypoints set around the football pitch and configured the AUTO mode on my radio controller. 

### First attempt
I had a really hard time getting the plane to stay up &mdash; it was very unstable, often rolling side-to-side with application of throttle. It was windy, but that couldn't possibly account for all this instability.

I had a closer look and found that the motor mount was tilted to the left ever so slightly. This meant that there was more air being thrust back towards the right side of the vertical stabilizer, relative to the left side. I took the plane back and did a dry test &mdash; where I would place the plane on a flat surface and monitor the yaw angle. Essentially, you want to get it to the point where it's not yawing when you apply throttle.

I made the modifications to the motor mount and confirmed the finding. I also updated the [pre-flight checklist](/teleport/resources/preflight-checklist) to include this dry-run test of the control surfaces.

### Second attempt

I took off in Stabilize mode into the wind, and would attempt to gain altitude before flicking it into AUTO.

That never happened though. As soon as I launched it, it struggled to move forward (relative to the ground, it was actually hovering in place!). It then started moving backwards as the wind picked up even more. I was able to gain altitude, but keeping things under control was becoming a serious challenge, even at full throttle.

In the interest of not losing the plane, I brought it down and decided to try again tomorrow.
