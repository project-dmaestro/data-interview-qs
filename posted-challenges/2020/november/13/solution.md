---
layout: default
---

# solution

The wording was a bit unusual to me, but I believed that the point of the challenge is to find the probability of the company having to replace the package; two or more gaskets would have to be broken. 

![](images/binomial.png)

I defined a few things from the problem:

- Probability of weapon being defective, **p** is 0.01
- Probability of weapon being functional, **1-p** is 0.99
- The goals was to find the probability of having two or more defective gaskets out of twenty in a box, **P(X >= 2) = 1 - P(X < 2)**.

P(X >= 2) = 1 - P(X < 2)
P(X >= 2) = 1 - [P(X = 1) + P(X = 0)]
P(X >= 2) = 1 - 

[back](./challenge.md)
