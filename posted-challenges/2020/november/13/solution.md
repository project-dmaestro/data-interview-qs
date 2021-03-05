---
layout: default
---

# solution

The wording was a bit unusual to me, but I believed that the point of the challenge is to find the probability of the company having to replace the package; two or more gaskets would have to be broken. 

![](images/binomial.png)

I defined a few things from the problem:

- The number of trials, **n**, is 20. That would be the number of gaskets in a box.
- The probability of failure defined as when gasket would be defective, **1 - p** is 0.01.
- The probability of success defined as when gasket would be functional, **p** is 0.99.
- The desired "success" defined as the replacement of a whole box, **P(x >= 2) = 1 - P(x < 2)**.

P(X >= 2) = 1 - P(X < 2)
P(X >= 2) = 1 - [P(X = 1) + P(X = 0)]
P(X >= 2) = 1 - 

[back](./challenge.md)
