---
layout: post
categories: teleport logs
---

I took it out for a flight and it was stable in steady flight. Whenever it banked though, it would roll like crazy and then eventually settle down. I'd watched [a video earlier](https://www.youtube.com/watch?v=JNvA7tutirc) on PID tuning and recognized the symptoms immediately. Still, I decided to let it fly in AUTO mode and see what happens. It flew really really far away, and then crashed on it's way back.

I was also surprised when I inspected the logs to find that it'd been overridden (I did some flying after the crash, and memory in the APM is circular and overrides previous logs when it runs out).

Changes made:
- PID tuning, specifically adjusting the 'P' (Proportional) value for Roll down from `0.4` to `0.2`. If it's still too high, I'll adjust accordingly.
- Erase logs before flying. Don't fly after attempt that you want to investigate.
