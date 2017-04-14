---
layout: post
---

Wow, I just finished the second technical interview. The question was one that I'd seen before, but never actually solved. It was in the Cracking the Coding interview book. It was as follows:

**You have a sorted array that's been rotated a random number of times. The array contains only integers, and all of the numbers are distinct. Implement a search method with best performance possible.**

Hmm, the best possible performance is binary search of course, in `log(n)` time, but what about all this rotation business. After talking through the problem, I was able to get a good footing &mdash; we can't just compare the mid[] element with the item we're searching for. We need to first understand what array elements are where, relative to the mid.

The way I did this was by realizing that there are really only two possibilites:
1. Either the array is properly sorted between mid and right (e.g. `[1, 2, 3, 4, 5]`)
2. Or, the array is not. It increases in value, then resets and starts over (e.g. `[3, 4, 5, 1, 2]`).

Ok, the rest is trivial. Here's my solution:

<script src="https://gist.github.com/yazinsai/2eaef4b1f26c0e4ae93ff006f4221a2b.js"></script>

Of course, the solution I wrote wasn't as pretty, but the concept was the same. I had to work it twice during the interview, but in the end the guy was a good sport about it all and the fact that I talked my way through the problem earned me some points.

Next step: on-site interview. I'm excited; it's my first ever on site interview and I really want to see where things go from here. I've applied to other companies in the hope that I'd be able to land other offers and start a bidding war. I need to be careful about what I tell Facebook and when.

