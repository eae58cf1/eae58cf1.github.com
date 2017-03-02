---
layout: post
categories: teleport logs
---

## New plane build
Luckily, I had a spare AXN on hand so I immediately got busy building it again (something I can now do in my sleep!). I decided to add in an FPV (First Person View) camera gear on the plane so that I can see what's going on at all times. I'm also going to be painting it bright colors, and adding a buzzer for an alarm.

I still want to give the APM a chance, but something tells me that I'll be better off moving to the Pixhawk PX4, or the [SP F3 controller](http://seriouslypro.com/spracingf3). I really want to get this tried and tested before my full-scale plane arrives (sometime early next week!).

I need to move quickly, but with zero tolerance for mistakes &mdash; certainly not ones I've done before (and there are plenty by now).

## Changes from previous models
I'm making quite a few changes from the previous models I've built to date &hellip; many prompted in an attempt to reduce the risk of the plane getting lost:

- Adding camera gear for FPV flying
- Painting it a really bright color (so I can see it in the sky)
- Adding buzzer so I can find it when it crashes
- Add telemetry so I can get plane information at my remote control
- Swapped the AXN motor for the Turnigy 2730-1300 (I don't have a spare AXN on hand)
- Configure failsafe on the transmitter

Again, I'll be following many of the best practices listed [here](http://beta.ivc.no/wiki/index.php/AXN_Clouds_Fly_Setup).

## The Build
Today, I spent most of the day setting up the Seriously Pro F3 board to work as the autopilot of choice for this flight. Thankfully, I was able to get the GPS working early on:

![GPS working on SP F3](/assets/projects/teleport/inav-working-gps.png)

I later started with the actual setup, including all the configuration for the RC, the calibration and everything else. I also painted it, though I ran out of spray paint after finishing the underbody:

![Painted the plane body](/assets/projects/teleport/spray-painted-mini-body.png)

I made the right side of the wing neon-green so I can tell which direction it's facing when it's in the air.

**Update 2-Mar**: Today, I configured the INAV and it's all set for a test flight. I also added the video camera and transmitter, as well as setup the video ground station. 

Pix below:

![Mini FPV camera](/assets/projects/teleport/mini-fpv-camera.png)

![Mini FPV screen](/assets/projects/teleport/mini-fpv-screen.png)


Tomorrow, I'll take everything out for a spin &hellip; if it works well, will go ahead and run the waypoint flight.
