---
layout: post
categories: teleport logs
---

I've started work on building the full-sized MyTwinDream that I received last week. This plane is HUGE and I can easily see how it can carry several kilograms of payload for delivery, in addition to the loads of batteries it'll need to go long range.

Since I [no longer have the Pixhawk](/teleport/logs/mini-waypoint-attempt-6/), I'll be using a Pixracer (a newer, smaller version of the original Pixhawk). I'll also be using a custom battery pack made from the LiIon cells I'd developed previously (but were too heavy to include in the smaller AXN).

- Installed and centered all of the control surfaces
- Installed the airspeed sensor
- Got the GPS working

![GPS working](/assets/projects/teleport/fullsize-gps-working.png)

**Update (March 17):**

- Connected control surfaces to flight controller
- Installed the radio receiver

It's worth noting that this is a fairly large plane &mdash; definitely the largest I've built to date. I've also got huge 11 inch propellers installed on the dual motors, so we're talking about huge amounts of thrust!

Here are some progress pics:

![Cables everywhere](/assets/projects/teleport/cables-inside-hull.png)

![Motor mount](/assets/projects/teleport/motor-mount.png)

![Plane in progress](/assets/projects/teleport/plane-not-complete.png)

I also finally received the other 40A ESC I was waiting for (I only had one), so now I can test the whole plane.

I'll be working on the Lithium Ion battery pack once I receive the copper rod I've ordered in order to make my own spot welder. I tried to find one in the nearby university, but they didn't have one (strange!).

**Update (March 20):**

Today, I went ahead and calibrated all of the RC channels. I also centered all of the servos and got them setup properly. I attempted to connect the analog airspeed sensor that I had previously used on the Pixhawk (by connecting it to the ADC port). The Pixracer does [**not**](https://www.rcgroups.com/forums/showthread.php?2576614-Pixracer-Autopilot-the-new-PIXHAWK-generation-is-available/page149) support the Analog airspeed sensor, so I ordered a digital one instead.

Other than that, I'm currently waiting on the Power Distribution Board with a built-in BEC that can output both 5V and 12V (I'll need the 12V for the LED strips on the planes wings so I can see it in the dark).

I was hopeful I'll be able to get a used car battery so I can do the spot welding of the Lithium Ion battery pack, but I tried a few nearby places and turned out short. I'm now searching for alternative high current sources (600A+). If all else fails, I'll just solder the battery terminals directly (though I risk damaging the cells that way).

**Update (March 22):**

Today I received the Power Distribution Module (with the built-in 5V/12V BEC) &mdash; that means I'm all set to get the plane ready for its maiden flight!

Here's a run down of the things I've done today:
- Added the landing gear. Wasn't going to do this at first, but this would be perfect for full autonomy &mdash; I can now set it up to takeoff on its own, without even me having to hand-launch it!
- Calibrated the ESCs. To do this, I had to fashion a Y-cable that connects both motor control signals to a single servo lead that I plug into the flight controller. Tested, and it worked perfectly. Motors are now both in perfect sync.
- Connected the Power Distribution Module to the ESCs and the flight controller. I'm using the Pixhawk power module (which has a built-in 5V BEC that I'm using solely for the flight controller). This feeds the current and voltage metered data to the flight controller for monitoring. All other electronics are being powered by the BEC on the power distribution module. 

![Landing gear](/assets/projects/teleport/plane-landing-gear.png)

![Internal wiring](/assets/projects/teleport/plane-internal-wiring.png)

![Power Distribution Module](/assets/projects/teleport/plane-pdm.png)

All that remains now is to connect the camera & on-screen display up &mdash; and put together the Li-Ion battery pack (this is going to be a massive 23,000mAh 4S pack that weighs over 1kg). Should keep it in the air for several hours.
