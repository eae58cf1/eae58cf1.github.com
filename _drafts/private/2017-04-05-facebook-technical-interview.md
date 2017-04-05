---
layout: post
---

I just finished the Facebook technical interview, my first ever interview at a tech company. Here's the low down.

I had practiced for the past 10 days of everything Algorithms related. I'd done Coursera courses, read the CTCI (Cracking the Coding Interview) and done tens of questions on Leetcode. I figured if I was going to do this, I'd better go all in &mdash; or don't do it all.

It was 11am, and here goes nothing. I was set to talk with [Matthias](https://github.com/georgi), a (potential fellow) Solutions Engineer from Facebook, based in Berlin.

## Questions

He started by introducing himself, and I proceeded to do the same. Most of my introduction was focused on my business accomplishments, and he was ready to talk about the technical side of things by the time we were done. I think he had the impression that I had absolultely no idea how to write a single line of code. 

We started of with a fairly simple problem. Given an array of integers, place the non-zero integers to the beginning of the array (in any order) and return the number of non-zero integers.

Examples:

Before: [1, 3, 0, 4, 5, 0, 9, 0], After: [1, 3, 4, 5, 9, 0, 0] and return '5'

Before: [1, 0, 2, 3], After: [3, 1, 2, 0] and return '3'

It doesn't matter what you do to the array after 'n' (the number of non-zero integers). They could contain anything at all. Oh, and no creating new arrays. Do it in place.

I ate this question for breakfast. I did *everything* right. Started off by saying the obvious: if I had my way, I'd just create a new array with the non-zero integers and return it's length. Since I can't, let's see what else we can do. I could start from the left and swap out any zero with an element from the right. But what if the right element is a zero too? Well, we could just have 2 pointers: one from the left, and one from the right. If we find a zero as we're iterating from the left, we'd just advance the right pointer until we get a non-zero item, and swap. We'll continue to do this until the two pointers meet.

Great! I implemented it, and tested for edge cases. I then spoke about the complexity (linear time complexity, constant space complexity). Bam, we're done right?

Nope. We had 10 minutes left, and Matthias decided that'd be enough for another question: this time, about linked lists. The question was: **how can you reverse a linked list, given a header node?**. Hmph, piece of cake.

Why, you could just use a stack. Iterate through the list, push the items into the stack and once you reach the end, just pop them out in reverse order.

Ok, how else? Hmm, we could use recursion. Make the recursive call first, and print on the way up (from bottom to top, as opposed to on the way down). That should do it.

Ok, how else? Hmmmm, let's see. We could modify the linked list to add a back pointer &mdash; effectively making it a doubly-linked list.

Ok, how else? I got the feeling he had a particular answer in mind. He did. He then proceeded to explain how we could *simply* reverse the list in place as we were going along.

To explain, if we had a list:

A -> B -> C -> D -> nil

We could do:

`B -> A` on the first pass, `C -> B -> A` on the second and so on. Till you get the reversed list.

With just a few minutes on the clock, he asked me to implement this solution. Ok, it seemed totally doable.

And then, blank.

I couldn't wrap my head around how this would work. I was staring at the blank method block:

```ruby
def reverse(head)

end
```

I wrote a bunch of incoherent stuff, but couldn't get the idea to snap in my head. Now, of course I can easily solve it:

```ruby
def reverse(head)
  current = head
  prev = nil
  while current do
    next = current.next
    current.next = prev

    prev = current
    current = next 
  end
  current # the new head
end
```

Essentially, the head becomes the lastest item we create, resulting in a reversed list. This insight, I missed. I could see how it worked in the example, but I couldn't translate it into code for some reason. It seems ridiculously easy now &mdash; you just reverse them &hellip; B -> A, instead of A -> B. But alas, it's water under the bridge now.

I'm almost certain I won't get through &mdash; they are supposed to have high standards, and this was a rookie mistake. I'm not sure why I didn't just google the answer &mdash; it would've taken 5 seconds. Alas, that doesn't matter either. 

It's over. I'm going to focus the next few months of my life on coming up with a viable SaaS business model &mdash; while spending a few hours a week brushing up on my algorithms and writing actual code. This will help in the event I decide to dive head on into this coding business again.

Overall, the experience was *easier* than I expected. I thought it'd be much harder because, you know, Facebook and whatevs. Nope. I oculd easily have aced it with more than 10 days of prep. That's reassuring.

I've still got it.
