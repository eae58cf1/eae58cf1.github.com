---
layout: post
categories: teleport logs
title: Scaled flight &mdash; Take 4
---
Since [the last attempt](/teleport/logs/mini-flight-take-3) we learned that we're going to have to shed some weight (or increase the thrust) in order to keep the plane in the air. That's what I'll be doing before this 4th attempt.

> Goal: Lose 123 - 143 grams

## Losing weight
Let's do an inventory of the heaviest items:
- Battery: 148g
- Power module: 41g (APM PM = 24g, Switch wire = 17g)
- APM: 32g
- GPS module: 28g
- Receiver: 19g (Receiver = 10g, Wires = 9g)
- Black plastic cover: 15g

To achieve the target, I'll be replacing the Li-Ion battery with a smaller 1,300 mAh 3S battery that weighs just 77g (including a switch I added). That's a savings of 71g.

I'll also lose the APM Power Module that weighs 24g. It's [pretty useful](http://ardupilot.org/plane/docs/common-3dr-power-module.html), but I just can't justify the weight.

That brings the total to 95g in savings. We're still about 30g short.

The GPS comes in a heavy plastic case. I removed that and this shaved off another 13g. I also won't be using the black cover on the front of the plane. That's another 15g in savings.

I could save 9g on the wires that are being used with the receiver (I'm using PWM, not CPPM which would require one wire instead of 6). However, the receiver I'm using doesn't support CPPM so I'll have to keep them for now.

The final tally is 71g + 24g + 13g + 15g = 123g! Just within the safe safe operating range  ⚖️

## Prep for flight
Made all of the changes referenced above, and did the final weigh-in:

![Final weigh-in](/assets/projects/teleport/take-4-weigh-in.png)

Great &mdash; we fit nicely into the safe operating range (between 550 - 570g). We're just about ready to go. I ran all of the checks on the [pre-flight checklist](/teleport/resources/preflight-checklist) and went out to the field.

When running the checks, it's worth noting that I had a really hard time balancing the Center of Gravity at the right spot. Even after moving the (smaller) battery all the way up the nose of the plane, it was still tail-heavy. I moved the receiver up front and it was still off. I decided to go ahead anyway. There's nothing more I could've done without adding more weight to it.

## Flying time
It was a really windy day (winds clocked in at about 30kph) but I decided to fling it up anyway. 

![Ready to go](/assets/projects/teleport/take-4-ready-to-go.png)

Fired it up and it flew like a beauty! I was easily able to pick up altitude in Stabilize mode and then flicked the Loiter mode on and it started circling on its own!

Even managed to get a video taken:

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMfMj3W4syc" frameborder="0" allowfullscreen></iframe>

There you go &mdash; it took 4 attempts, but it finally worked! Phew, now I can check this off.

## Later &hellip;
I went home and charged up the battery so I could take it for another spin. When I plugged it in, I got a whiff of a burning smell. Then I saw smoke coming out of the APM!

I immediately turned it off, but the damage was done &hellip; my APM died:

![Dead APM](/assets/projects/teleport/dead-apm.png)

I still don't know exactly what the cause might've been &mdash; it could've been because I had inadvertantly placed some insulation tape on the AMTEL chip. Who knows? Luckily, I have a spare APM so the plan won't get impacted.

Overall, doesn't matter though &hellip; it worked!

![First working flight](/assets/projects/teleport/take-4-worked.png)
