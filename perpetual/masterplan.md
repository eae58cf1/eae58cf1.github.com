---
layout: page
categories: perpetual
title: Masterplan
published: false
---

My goal is to create a plane capable of perpetual flight. 
<!-- (If you're curious you can find out more about my motivations for building this project [here](/masterplan/)) -->

## Challenges

None I can foresee, since I know absolutely nothing about plane-building! 

So I've got a lot of things to learn. Thankfully though, we live in a day and age when many people on the plane (my lucky self included!) have access to the sum of human knowledge at our fingertips. This'll make things easier. I'll attempt to work on both the textbook (theoretical) and field (practical) fronts.

## The Plan

I'm breaking this down into 3 pieces that I will work on in parallel. These pieces all relate to their "power role" in the plane:

- Consumption: The drive system &mdash; which consists of motor(s)
- Storage: The batteries
- Generation: These systems are responsible for generating power (that would be used for charging the batteries, and keeping the plane moving). Most likely going to be solar cells.

Makes sense? You bet it does.

Now, if we can find out how much power the plane will need to stay in the air, we can determine how much storage we'll need to keep it up at night (when we can't generate power). We'll also need to know how much power we can actually generate during the day. If it's not enough to cover the power consumption PLUS recharge the depleted batteries, then we're not going to make it.

Before getting lost in the details of each individual box, it's worth highlighting an issue I noticed from the beginning. Take a look at the figure below, which shows the interaction between all the different design parameters we'll need to pick:

<img src="/assets/projects/perpetual/masterplan-parameters.svg" title="Dependency illustrated">

You may have noticed a couple of circular references there. Here's one:

> Total Weight -> Total Power -> Battery capacity required -> Battery Weight -> Total Weight *(and so on &hellip;)*

Essentially, we need the total weight to find the total weight. **Catch 22**

The solution to this would be to simply plug some numbers in and play with them. You can use loops to simulate a range of meaningful values for power, weight, etc. and then see what combinations work.

## The Goal

Having briefly mentioned the different systems involved, it's a good idea to state a clear goal for our plane. Ours is to use up as little power as possible. The less power we use (on the motor), the less we have to store (via batteries) and the less we have to genereate (via solar cells).

So that's the goal: reduce the power consumption on the plane. The bit that uses up the most power on our plane will undoubtedly be the motor.

But why do we need a motor in the first place? To overcome drag. Not to keep the plane in the air (that's what lift does), but to keep it moving forward (so it can generate the lift it needs to stay in the air).

So let's revisit that goal &hellip; in order to reduce the power required for the plane, we need to reduce the opposing drag. The lower drag, the less work we need to do to overcome it.

So that's our specific goal then: to design a plane with the least possible drag.

{% comment %}
Let's take a closer look at what needs to be done in each section.

### Power Consumption (Drive System) 

Again, this part seems trivial, at first. We can easily figure out how much power a damn motor needs, I hear you say. "Just connect a wattmeter!". Wait &hellip; didn't we just talk about how the other systems are interconnected? To accurately determine the power we need, we would have to know the weight of the plant &mdash; which requires knowledge for the power we need. 

To kick start the process, we're just going to pick any low kV motor initially and calculate the other figures. Why a low kV motor though? Well, you can find an explanation of the logic behind this [here](/perpetual/lessons/motor-efficiency).

Once we've calculated our actual drive, generation and storage values with this configuration, we'll review these initial design choices to see how we can optimize things.

So, as far as power consumption goes, here's what we'll need to work out:

- Design/pick the plane body
- Choose a motor/prop
- List down the weight all of the components we'll need
- Test flight to make sure it can actually fly under those parameters

TODO: We've implicitly assume that we're using a plane body, explain why

### Power Generation (Solar system)

TODO: Do you really need 200%? OK, 100% of power to run motors ... but how much to charge cells over the daylight period?
TODO: using diodes to avoid series issues with shading http://www.solar-facts.com/panels/panel-diodes.php  
{% endcomment %}
