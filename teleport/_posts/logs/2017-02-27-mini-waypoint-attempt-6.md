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

## Flight with F3

Test flight did not go well, and I continually suffered with getting the F3 to ARM with the GPS in place. I finally relented and removed the GPS, since the initial flight was not going to be using the GPS modes anyway (I just wanted to get the thing trimmed and stable). When I threw it up in the air, I found that it wasn't stable at all (despite being in Stabilize mode). 

I tried once more with similar results. I'm sure I probably could've got the damn thing to work with a bit more fiddling about but I felt like I'd wasted too much time switching between platforms and trying to re-learn them. Instead, I decided I'd just go back to either the APM or Pixhawk &mdash; let's hope we make quicker progress that way.

## Pixhawk PX4 configuration

Switched to Pixhawk. Had to setup with the following:

- I was using an **analog** airspeed sensor connected to the ADC at the bottom right corner of the board. In order to get QGroundcontrol to recognize it, I had to [set the `SENS_DPRES_ANSC = 1000`](https://pixhawk.org/help/aspd).
- In the end, the sensor was too heavy so I had to remove it (and [disable it](https://pixhawk.org/firmware/parameters#circuit_breaker) by setting `CBRK_AIRSPD_CHK = 162128`)

Today I took it out for a test flight:

![Pixhawk flight ready](/assets/projects/teleport/pixhawk-flight-attempt-1.png)

![Pixhawk flight ready](/assets/projects/teleport/pixhawk-flight.png)

I originally set it up in just Stabilize mode, and it flew really well despite 30km/h winds. Alas, I flew it too low and crashed into a tree breaking off half the right wing. Thankfully, it was nothing a bit of UHU Por couldn't handle. The bigger problem was getting the Pixhawk to stay in place &mdash; it's always challenging getting it to sit tight in a foam plane. I've tried double-sided tape but it comes loose after almost any crash &mdash; no matter how minor.

Flight controllers (and the Pixhawk especially) are incredbily sensitive to axis turns. Finding a wayto mount it in a tight spot like the one I have in the AXN is an ongoing struggle &mdash; though it won't be as big an issue in the full-scale MTD.

Having got these basic modes working, I proceeded to setup some [GPS-assisted modes](https://dev.px4.io/concept-flight-modes.html#flight-mode-quick-summary). I used Position (which essentially maintains the same heading and altitude at neutral input) and Loiter.

I never did get a chance to try Loiter, but the Position flight worked like a charm. I had a few rough landings though in the high wind, and this meant the PX4 kept nudging about &mdash; until I eventually called it a day.

Tomorrow, I'll attempt Waypoint flight on the Pixhawk.
