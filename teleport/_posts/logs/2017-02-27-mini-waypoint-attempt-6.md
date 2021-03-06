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

## Test waypoint flight

I configured the Pixhawk using Qgroundcontrol. I don't have an SD card handy, so I can't use the onboard logging capability on the Pixhawk (It'll be a few days before I get the one I ordered). Still, we're going ahead anyway and hope everything works as expected. I'd like to have Telemetry on the plane so I can see how it's progressing.


I made a few mods before the flight:

- I installed a balsa wood base below the Pixhawk to keep it stable. I just used UHU Por to glue it in place, with the battery underneath. I should still be able to charge the battery without removing it, since the balance connector lies above the board. I also added some aluminum foil to the base to protect from interference to the magentometer resulting from the power lines underneath. I attached the Pixhawk to the board using double sided foam tape, which would double as a vibration dampener.

![Balsa wood base](/assets/projects/teleport/balsa-wood-base.png)

- Noticed that the frame was broken from the underside, so my faithful tube of UHU Por was summoned once again &mdash; it didn't fail me.
- I also followed every item on the pre-flight checklist, which was good because I found the magnetometer calibratoin to be off and the prop unbalanced.

I tried setting up the waypoints for GPS flight but it turns out it needs the SD card too (which I don't have on hand). I ordered one off Amazon and should be getting it tomorrow.

![Configured waypoints in QGroundcontrol](/assets/projects/teleport/configured-waypoints.png)

![Waypoint attempt 6](/assets/projects/teleport/waypoint-6-attempt.png)

I already had the plane ready, so I took it out for a spin to test the non-GPS flight modes again. It flew really well &mdash; and I was having so much fun that I forgot about the battery until I tried bringing the plane back from a field about 500m away. It seems to have run out of battery half-way through its journey, ultimately crashing on a side road.

I picked up the pieces and brought it home &mdash; the 3S battery was at just 8.4V (that's 2.8V/cell)! The minimum voltage for a LiPo cell before you start getting irreversible damage is 3.2V/cell. I went straight home to recharge it.

The battery is rated at 850mAh but it was so drained that it charged all the way up to 908mAh:

![Waypoint attempt 6 - crash](/assets/projects/teleport/waypoint-6-crash.png)

![Battery i'm using](/assets/projects/teleport/battery.png)

![Battery charged at higher than rated!](/assets/projects/teleport/waypoint-battery-charged.png)

I'll fix the plane now, in preparation for tomorrow's *real* GPS waypoint flight.

**Update:** Attempted to launch this baby today (March 7) but the GPS wasn't working, and I still hadn't received the SD card. I ended up replacing the NEO-M8N with the previously working NEO-7M (this is the second GPS I've now replaced in a week, so our friends in China obviously seem to be having some serious quality issues). By the time I got the SD card and replaced everything out, it was dark. Will launch first thing tomorrow morning inshallah!

**Update2 :**

Attempted to fly today early morning:

![Early morning flight](/assets/projects/teleport/waypoint-6-early.png)

It was super wet. I fired up the plane in AUTO made and threw it in the air. It was supposed to auto-start the motor and take off, but it did not. Looks like there's some special configuration I'll need to do to the Pixhawk to make it automatically take off. Instead, I decided I'd launch it in Stabilize mode, gain altitude and then switch to Auto mode. I was able to take off, and once I switched to AUTO the plane did change course towards the first waypoint. However, it struggled with the wind, and just kept lost altitude until eventually crashing into the ground.

I went back to the workshop with the following changes in mind:
- Setup auto takeoff.
- Reorient the waypoints considering the wind direction. I should launch into the wind (i.e. upwind) and land upwind as well.
- Secure the battery in place, since it seemed to have come off after the crash landing.

Intent not to waste more time, I went right to it &mdash; finding out early on that there's a TAKEOFF waypoint type that I should be using instead of just the standard WAYPOINT. That takes care of the first item. When it came time to update the waypoints I noticed that I wasn't able to write the updated waypoints to the Pixhawk.

After a lot of fumbling about, I realized that this worked well in Arduplane but not on the Pixhawk firmware:

![Pixhawk firmware unresponsive](/assets/projects/teleport/pixhawk-config-issue.png)

I switched to Arduplane and had to recalibrate everything, and setup the correct parameters. 

These params are:
- `TKOFF_THR_MINACC = 10` (m/s/s, acceleration for hand launched plane)
- `TKOFF_THR_DELAY = 2` (s/10, delay before triggering motor in tenths of a second)
- `TKOFF_THR_MINSPD = 3` (m/s, groundspeed before motor is engaged)
- `TECS_PITCH_MAX = 25` (deg, this is the maximum pitch angle it'll use when climbing)

I then checked the control surface directions, and had to reverse the RC channels for Aileron and Rudder.

After updating the flight modes to Stabilize, Loiter and Auto (i'm using a 3 position switch on my transmitter for controlling flight mode), I was ready to update the waypoints, which I promptly did.

Now, to fly.

I went out, this time finally having made sure that it would work well. Everything was setup &hellip; I did a final check of all the control surfaces, and it worked great. I armed the motor and started increasing the throttle. Nothing. That's weird. Tried again, this time checking to make sure the throttle was OK. Still nothing. 

Oh great.

I did a few checks using the Tower app on my phone (connected to the bluetooth module that I connected to the Telemetry port on the Pixhawk). Everything was armed and OK. I took it back to the workshop and found the ESC to be faulty:

![Faulty ESC](/assets/projects/teleport/faulty-esc.png)

Oh great. I replaced it, and it was dark &mdash; now to wait patiently until the morning for the test flight.

**Update 3**:

![Attempt X](/assets/projects/teleport/waypoint-7.png)

- Take off was perfect (right into the wind), and first 3 waypoints flew perfectly
- The next few waypoints it struggled with, especially when it had to go against the wind. Eventually, the wind got faster than the plane itself and it started sliding backwards. 
- After a few minutes, it crashed and lost. I know, i know. I had no FPV, no Telemetry and no GPS coordinates. I didn't even have a buzzer on it so I could locate it by ear.

<iframe width="560" height="315" src="https://www.youtube.com/embed/QARcVOCR7tY" frameborder="0" allowfullscreen></iframe>

While the plane did disappear, I consider the mission a partial success.
