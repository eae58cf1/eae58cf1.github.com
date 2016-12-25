---
layout: page
categories: perpetual logs
title: Intial wing design parameters
---
The purpose of this step is to come up with some sort of initial design for the aircraft wing. This would include span, chord and airfoil shape &mdash; as well as thickness of the wing. We're going to be using expanded polystyrene (EPS) foam for the wing material since that's all I have available. Ideally, I'd find something to laminate it with in order to reduce it's Reynolds number.

<!-- update previous post to talk about reynolds number -->

Since I don't know much about wing design, besides [the guidelines we discussed](/logs/general-guidelines-for-wing-design) in the last post, I'm going to use the help of a simulator. The specific one I'll be using is [NASA's FoilSim III](https://www.grc.nasa.gov/WWW/k-12/airplane/foil3.html) &mdash; which I found really surprisingly easy to use.

**Note:** It's easy to use but it was a nightmare to setup. I had to create a Windows virtual machine (since I'm running a Mac) and install the Java SDK and disable all security settings before I could get the 15 year old Java applet to finally run.

![NASA FoilSIM III](/assets/projects/perpetual/nasa-foilsim.png)

## Goal
Before messing around with the FoilSim app, just keep the design parameters in mind:

$$ \text{Lift} = \text{Plane Weight} + ~30\% $$

The 30% there is a buffer.

Also,
- Low wing loading (\\(\lt 50 kg/m^2\\))
- High aspect ratio

While we'd normally need some sort of weight measurement, I'm going to consider 1.5kg as a good starting point (for batteries, solar cells and wing body) considering a miniature version of our plane. At the end of this exercise, we'll consider whether this is a meaningful number or not &mdash; but let's not let that hold us up for now.

Here's what we expect to get from FoilSim:
- Drag, in Newtons (which is the force that our motor will need to overcome)
- Speed (to tell us what speed we should fly for efficient energy consumption)
- Stall speed (we need to **always fly above the stall speed**)
- Wing dimensions (span, chord, airfoil shape)

## FoilSim time

While messing with FoilSim, I learned a few things that I really should clarify:
1. The lift changes with angle of attack (the incline of the wing, relative to the horizontal plane). I considered the \\(\text{Lift} = \text{Weight} + 30\%\\) guideline above at the neutral angle of attack of \\(\alpha = 3 \deg\\). 

Here's the result:

![NASA FoilSIM III](/assets/projects/perpetual/nasa-foilsim-results-v1.png)

I had to pick a higher speed of 30 km/h in order to get the necessary lift (16N &asymp; 1.6kg). Here's the raw output data in txt format ([View wing data](/assets/projects/perpetual/airfoil-v1.txt))

{% comment %}
## Determining plane weight
I'm going to run a quick off the cuff calculation of the plane weight that is very, very approximate. Now, the main factors affecting our plane weight (as detailed in [the Masterplan](/perpetual/masterplan)) are going to be:
- solar cell weight
- battery weight

We can't determine either of those things without first knowing the power consumption (which would be derived from the plane drag).

To bootstrap this process, I'm going to assume &mdash; just based on my brief research on the Internet &mdash; that we're going to be consuming about 50 Watts of power. Now, Watts is a rate (sort of like speed) of energy consumption, so we're essentially saying that the motor will be consuming 50 Joules/second. Ok, now we need to determine the battery weight and solar cell weight.

$$ \text{Stored Energy required} = \text{Num. of hours without sunlight} * \text{Power} $$

The energy consumed per hour is our Power (50W) and the number of hours without sunlight for the UK in the month of January 2017 [is 16 hours](http://jan.moesen.nu/daylight-calculator/?location=London%2C+United+Kingdom&latitude=51.5073509&longitude=-0.12775829999998223). This makes a total of \\(16 * 50 = 800 Wh\\), where \\(Wh\\) is Watt hours (a unit of energy). The [18650 cells](https://batterybro.com/blogs/18650-wholesale-battery-reviews/88881030-5-common-lithium-ion-battery-myths-explained) I plan on using, which are the same that Tesla uses in their cars, have a specific energy of about 250 Wh/kg. That means that we'll need \\(800 \text{Wh} \div 250 \text{Wh/kg} = 3.2kg\\)

Wow, that's a lot of battery weight! And we haven't even talked about the solar cells yet. Let's do that now.

The [Sunpower C60 cells](http://www.sun-life.com.ua/doc/sunpower%20C60.pdf) I'm considering seem to offer the best power/weight ratio based on my initial discussions with a friend that knows alot about solar. They generate about 

{% endcomment %}

