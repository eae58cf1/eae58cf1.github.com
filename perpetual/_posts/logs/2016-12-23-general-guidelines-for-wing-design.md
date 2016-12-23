---
layout: post
categories: perpetual logs
title: General guidelines for wing design
---
[We've already decided](/perpetual/logs/aircraft-form) we're going to be using a fixed-wing body. Now, before proceeding with desigining an efficient plane structure, I was able to do some research to get a general sense of what the important design considerations are, and what sort of values each one should have in order to operate in a reasonably efficient manner.

Again, the plane we design as a result of this first exercise will most certainly *not* be the most efficient, but we want to get that real-world feedback from building it ASAP. That means compromises. I don't want to spend a ton of money, or time, reading up on everything related to Aerodynamics!

So here's a list, in no particular order, of the important parameters we're considering for this design.

## Wing Loading

Wing loading is a measure of how much weight the wings of an airplane are carrying (since the wings are the surfaces that generate lift in fixed-wing aircraft). This is important because it has a really big impact on the performance characteristics of the plane.

$$\text{Wing Loading} = \frac{\text{Mass (in kg)}}{\text{Wing area (in }m^2\text{)}}$$

Planes with a lower wing loading have less weight being carried relative to their wing area. Examples of these include gliders, which typically have a wing loading of less than 50 kg/m<sup>2</sup>. On the other end of the spectrum, large passenger airplanes are designed to have a ridiculously high wing loading. The A380 has a wing loading of 663 kg/m<sup>2</sup>!

Here's a table that compares low wing loading with high wing loading:

| **Low wing loading** | **High wing loading** |
|------------------|-------------------|
| more efficient, less thrust required to achieve lift | less efficient, more thrust needed to achieve lift  |
| slower (more drag) | faster (less drag) |
| climbs faster | lower rate of climb |
| can make tight turns | turns not as tight |
| less stable during turbulence | greater resistance to turbulence |

It's pretty clear from the table above that when designing an efficient aircraft, we want to have **low** wing loading. Stability is going to be a challenge, but that's something we'll try to address down the road at some point.

Once additional thing worth discussing is the impact wing loading has on the take off and landing speeds of the aircraft.  The velocity of an aircraft is proprotional to \\(\sqrt{W_S}\\) or \\(\sqrt \frac MA\\). That means that for a 10% increase in Area would reduce the takeoff velocity \\(v\\) by \\(\sqrt \frac{1}{10\%}\\) = 5%

I found [the Wikipedia page on Wing Loading](https://en.wikipedia.org/wiki/Wing_loading) to be an excellent reference on the topic.

## Aspect Ratio

While wing loading is concerned with the wing area, aspect ratio is related to the actual dimensions of the wing &hellip; specifically, the ratio between a wings span (length from one tip to the other) and its average chord (roughly the distance from the front of the wing to the back).

$$ \text{Aspect Ratio} = \frac{\text{span}}{\text{mean chord}} $$

Wings with higher aspect ratios are more energy efficient because it is more efficient to move alot of air slower, than a little air faster (I described this in detail [here](/perpetual/lessons/motor-efficiency)).

That's what we want to hear! Again, gliders like the [Eta motor glider](https://en.wikipedia.org/wiki/Eta_(glider)) have a *really* high Aspect Ratio of more than 70, whereas the Airbus A380 is about 8.

Some disadvantages to heed with high aspect ratio wings is:

- Maneuverability: they have higher roll angular acceleration (which means that they tend to be unstable around the clockwise and counterclockwise axes). This shouldn't be an issue for us, since our onbaord computer will handle stabilization of the aircraft (more on that later)
- Structural: long wings tend to break easier. We need to make sure we've got them reinforced, perhaps using carbon fiber rods in the wings or struts under the wing for support.

## In summary
Our efficient plane should have:

- Low wing loading
- High aspect ratio
