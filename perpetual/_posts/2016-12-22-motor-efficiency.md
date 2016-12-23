---
layout: post
title: Motor Efficiency
categories: perpetual lessons
excerpt: |
  In this post, we discuss what things you need to consider when picking a motor for your efficient aircraft.
---
Planes fly when motors fling air around, usually in the opposite direction of motion (i.e. for fixed wing planes, the motors pushes air back in order to move the plane forward).

Now, when selecting a motor for efficient flight, we have a pick between low kV motors and high kV motors. The kV rating is just a measure for number of revolutions per supplied Volt, when you haven't put any load on the motor.

A 2200kV motor supplied with 11.1 volts would spin at about 2,200 * 11.1 = 24,420 rpm (again, this is with no propeller on).

So big kV numbers mean the motor spins really fast, and smaller kV motors means it spins slower. Fast spinning motors can afford to use smaller propellers (and as a result move less air, but faster) and slower moving motors are usually coupled with bigger propellers (spinning more air *slower*).

## Which is more efficient?

Low kV motors, with big propellers.

Why? The logic is simple, and relies on the formula for Kinetic Energy:

$$K.E. = \frac12 m v^2$$

The total kinetic energy (or work) required to move a bunch of air is dependent on the mass of the air (\\(m\\)) and the square of the velocity (\\(v^2\\)).

The key is in the squared velocity, coupled with Newton's second law \\(F = ma = m \frac{\Delta v}{\Delta t}\\). It's clear that Newton gives you the choice of either expelling more mass, or increasing the velocity change \\(\Delta v\\) in that expelled mass &mdash; they both have a proportional impact on the resulting force.

However, we'll choose more mass (over velocity) every day of the week &mdash; since we now know that the required kinetic energy will be lower for a larger mass flung at a smaller velocity,
