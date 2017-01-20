---
layout: page
categories: teleport
title: Masterplan
---
# Start with the Why

My goal, over the next few months, is to find a solution to a problem that humanitarian aid agencies face in places across the world: **the logistics issue of delivering supplies to towns and cities under siege**. 

We all witnessed the aftermath of [Madaya](http://www.cnn.com/2016/01/09/middleeast/syria-madaya-starvation/index.html) and numerous other Syrian cities, where people starved to death while aid agencies just 30km away couldn't get through to help them until the situation reached it's most dire state. It's shocking they don't seem to have any recourse outside of [waiting for the perpetrating governments](http://www.cnn.com/videos/world/2016/01/20/ban-ki-moon-speaks-about-madaya-war-crimes-curnow.cnn) to reach some sort of resolution. With every passing day, children and families perish.

> that most people in hard-to-reach and besieged areas remain difficult for the United Nations and their implementing partners to reach with humanitarian assistance, (UN Security Council [Resolution 2191](http://unscr.com/en/resolutions/doc/2191))

This is the 21<sup>st</sup> century. We can do better. After messing around with UAV's (Unmanned Aerial Vehicles a.k.a drones) in my spare time, I found them incredibly potent. Today's technology easily allows small planes (no larger than 2m in wingspan) to do 100km+ trips on a single charge with a payload of several kilograms. That means that the solution to this problem is already *technically* within our reach.

My goal is to **provide individuals everywhere with the means to directly contribute to support the people in need**.

# High level plan

My focus for the past few weeks, before the break started, was on [building a perpetually flying UAV](/perpetual). The idea being that, if you can build a plane that flys forever, then everything else is easy. Want to add payload, fine. That's easier to do. Essentially, the idea is to tackle the most difficult problem head-on and see what transpires: range.

The only thing is, this takes *serious* time. The payout is also unclear. What will I gain when I do actually build this thing? How does it fit into the goal of aiding the people in need in Syria and elsewhere?

The answer is it doesn't; not directly. Back to the main plan then.

If my goal was to optimize for helping people in need, how can I go about that in the quickest and most effective way possible? The answer is, get results quickly. If that means getting a ready-made UAV and doing a simple flight into Syria and back -- even with a basic drop of just an orange -- that's fine. That'll get you a small win early on; something you can use to generate more positive feedback, and get to the greater goal in smaller steps.

Working alone isn't easy, and this is a great way to maintain motivation -- while achieving the results you set out to tackle. 

This is such a big problem, and having an intense focus is going to be crucial -- both for following up on progress, as well as for managing the very limited resources you have (as an individual). 

By getting some concrete results early on, you could gain funding for a progressively bigger impact from sponsors. This is - after all - the essence of the Lean Startup way. 

It's not to bet everything on a peripheral goal. But to get to the point we're you're celebrating a small win, early on -- bite-size wins that can sustain bigger ones downstream.

My two cents. I think it's pretty clear what I would do next.

# Details

Ok, the high level bit was relatively easy to do once I'd written it down. Now for the tricky bit: how do you actually implement this in real life?

Well, let's recap the high level goal for now, and find a way to achieve small wins. Start with a basic win -- start with one person in, say, the border towns on the Lebanon/Syria or Turkey/Syria border delivering a tiny item (e.g. an orange). 

That's 3 restrictions here:
- one person
- low range
- low payload

We'll work on alleviating each of those 3 restrictions at a later milestone, but for now, I can live with that.

Ok, so even to get to this point -- a point where we can do this super-restricted test is going to need quite a bit of work. Firstly, we need to do a test to make sure that we can get a tiny range covered and back. I had a look at Google maps and it looks like the Turkish border city of Antakya is about 27km from the Syrian town of Salqin. If you can get a UAV that can go out 30km, and then fly back -- then you're in business.

![Distance required for mission v0](/assets/projects/teleport/mission-v0-distance.png)

There are some restrictions though. Assuming you're going to be bringing this to Turkey somehow, you're going to need to have some sort of way of putting this together yourself using very basic tools. You can bring in a motor, some carbon fiber struts, a Pixhawk and even some batteries. An airframe might be too big to bring in, unless it can be easily disassembled and reassembled.

So we have:
- low wing span (or something bigger that can be built using materials on site)
- low cost (so experimentation doesn't cost and arm and a leg)
- have a basic release mechanism, for dropping the orange
- video, for proof

## Previous work

Spotted a few videos on Youtube showing long range, variable payload flights:
- [15km](https://www.youtube.com/watch?v=Wyky6my9yFY)
- [80km](https://www.youtube.com/watch?v=z_PxhU9i9Ng)
- [100km x 2!](https://www.youtube.com/watch?v=JFiXa_urctQ)

Also, read about a project (now defunct) called the [Syria Airlift project](http://syriaairlift.org) started in Stanford, CA. The project doesn't seem to have gotten very far beyond a prototype &mdash; they did no pilot runs in Turkey/Syria as far as I can tell. More on that [here](http://www.afcea.org/content/?q=node/13875).

## Legal stuff

While the UN has already approved and passed resolutions supporting the "non-consensual delivery of humanitarian aid" to Syria, Turkey still has rules around drone use. I [had a look](http://uavcoach.com/drone-laws-in-turkey/) and it seems that they are pretty stringent (all flights, including those of model aircraft have to be pre-approved by the Civil Aviation Authority there). Lebanon appears to be [more lax](https://uavsystemsinternational.com/drone-laws-by-country/lebanon-drone-laws/), though as a party to the conflict they might not be so supportive.

Excerpt of UN resolution below:

> Decides to renew the decisions in paragraphs 2 and 3 of Security Council resolution 2165 (2014) for a further period of twelve months, that is, until 10 January 2018; -- <cite>[UNSCR 2232](http://unscr.com/en/resolutions/doc/2332)</cite>

It'd be worth talking to aid agencies in both Lebanon and Turkey, as well as the UN somehow. If you know someone who can help, please [get in touch with me](mailto:hi@yaz.in).
