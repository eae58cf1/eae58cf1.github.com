---
layout: post
categories: teleport logs
---

### Gale force winds

The next day, we had gale-force winds. Not a good day for science:

![Gale-force winds](/assets/projects/teleport/gale-force-winds.png)

### Third attempt

Today was the perfect day for the next attempt. I took the plane out in the morning and ran all the pre-flight checks:

![Take 5](/assets/projects/teleport/axn-take-5.png)

The plane was stable, but it had trouble gaining altitude. I'd checked the weight and that definitely wasn't it. There was a bit of wind but not enough to hinder ascent. I don't have an airspeed sensor on this mini-aircraft so I don't know if the wind was an issue (airspeed - ground speed from GPS would tell me the net wind speed at the nose). It really was quite strange. I flicked it into Loiter mode at about 20m up and it started to lose altitude so I switched it back to Stabilize mode. The battery wasn't running at 100% (the voltage was close to 11.6V) but that couldn't be it either.

When I inspected it up close, I noticed that the motor mount was loose (probably from a few previous landings). The mount itself was supposed to be screwed onto the body, but the nut had fallen off and was now held together by some tape. I didn't think it was an issue since this was a pusher configuration and there wouldn't be separation stress on the mount. I might've been wrong though. A wobbly motor could certainly qualify as a contributing factor.

Changes made:
- Updated `THR_MAX=100` (it was previously 75, which limited the maximum throttle value that the APM would apply).
- I fixed the motor mount down with some wood screws that were significantly larger than the original holes. This gave me a very strong hold, without the need for a nut on the other side of the mount.
