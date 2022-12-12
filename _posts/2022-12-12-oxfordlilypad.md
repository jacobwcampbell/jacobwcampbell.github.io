---
layout: post
title:  "Oxford Lilypad Interview Question"
date:   2022-12-12 17:19:00 +0000
categories: technical computerscience maths
usemathjax: true
---

During my interview practice I came across a neat problem entitled "Lily-pad lunacy". This is a previous-year Oxford interview question found [here](https://www.cs.ox.ac.uk/admissions/undergraduate/how_to_apply/sample_interview_problems.html).

The Question is as follows:
> Lily-pad lunacy. Eleven lily pads are numbered from 0 to 10. A frog starts on pad 0 and wants to get to pad 10. At each jump, the frog can move forward by one or two pads, so there are many ways it can get to pad 10. For example, it can make 10 jumps of one pad, 1111111111, or five jumps of two pads, 22222, or go 221212 or 221122, and so on. We'll call each of these ways different, even if the frog takes the same jumps in a different order. How many different ways are there of getting from 0 to 10? 

To start with I decided to look at smaller problems, and calculated some values.

I am going to express the number of different ways of traversing the lilypads as a function L of the number of lilypads n.

$$L(n)$$

![Sample Values](/assets/img/img_2022-12-12-oxfordlilypad_1.png)

From this we can see a pattern emerging for a recursive relationship.

It appears that to work out the possible number of combinations, we can look at the possible number of combinations if we jumped forwards 1 space, or jumped forwards 2 spaces.

To represent this as a recursive formula we can write:

$$L(n)=L(n-1)+L(n-2)$$

```python
def L(n):
    if n < 3:
        return 1
    else:
        return L(n-1) + L(n-2)
```

for L(11) we get 89 possible paths, which is correct.