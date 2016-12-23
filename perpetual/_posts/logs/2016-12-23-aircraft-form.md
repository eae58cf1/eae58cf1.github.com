---
layout: post
categories: perpetual logs
title: Aircraft forms
excerpt: |
  Before we try finding the optimum design parameters for a plane, we need to decide on a lift vehicle form. The most popular is the fixed wing "aeroplane" design, but we're going through all of them to take our pick.
---
Before we can start designing the aircraft, we need to decide on what sort of aircraft it's going to be. The most popular form is the fixed-wing plane (like the one shown below), but it's certainly not the only choice.

![Fixed wing plane](/assets/projects/perpetual/fixed-wing-plane.png)

Other forms include:

- Quadcopters
- Buoyant flight (e.g. airships, hot air balloons)
- Helicopters

When deciding on the type of vehicle that we need to use, we need to consider all of our requirements, namely:

- That we want to use as little power as possible (as explained in the [Masterplan](/perpetual/masterplan))
- That we have a sufficiently large surface area (in order to lay out the solar cells for power generation)
- That it's reasonably small. I don't have a spare hangar where I can build this thing out, so &hellip; yeah, small.

## Quadcopters
There are a couple of reasons why these may not be a good idea:

- They have 4 motors, which means they're going to suck a lot of power. Also, they have a small surface area which means we're not going to be able to generate much power via solar cells.

## Buoyant flight (Airships)
This actually sounds pretty reasonable. Using an airship means you won't require any vertical thrust to carry the aircraft since it relies on the principle of buoyancy to achieve lift. Atmospheric pressure exerts a force on objects that are less dense than the surrounding air, causing them to rise.

A beautiful solution, that doesn't rely on any sort of fuel to move! Alas, there are a few downsides:

- They need to be pumped with gases that are lighter than air. Lighter-than-air gases include Hot air (like a hot air balloon which would require a combustion fuel for heating), Neon (rare, expensive), Ammonia (poisonous), Methane (flammable), Hydrogen (extremely flammable) and Helium (expensive). Here in the UK, Helium costs about [&pound;100 per m<sup>3</sup>](https://www.boconlineshop.com/shop/en/uk/helium-110745-101) (~$125). 
- They are huge, since you need to displace a large amount of air to compensate for any sort of added weight. Consider that air has a density of 1.29 kg/m<sup>3</sup>. If you're using Helium to lift the airship (Helium has a density of 0.164 kg/m<sup>3</sup>), then you get just 1.1 kg of lift for every m<sup>3</sup> of the gas. That means you'll need several m<sup>3</sup> to get anything useful up in the air.

## The remaining contenders
This just leaves Helicopters and Fixed Wing airplanes. While both could technically work, [fixed wing airplanes are more efficient than helicopters](http://aviation.stackexchange.com/a/5192/18340).

Fixed wing airplanes have a lower Lift/Drag ratio (something we'll talk about in the next post) than Helicopters.

Ladies and gents, we have a winner. **We're going ahead with a fixed wing aircraft!**
