---
layout: default
---

# solution

The wording was a bit unusual to me, but I believed that the point of the challenge was to find the probability of the company having to replace the package; two or more gaskets would have to be defective. 

![](images/binomial.png)

I defined a few things from the given information:

- The number of trials, ![](https://latex.codecogs.com/svg.latex?n) is 20. That would be the number of gaskets in a box.
- The probability of failure defined as when gasket would be defective, ![](https://latex.codecogs.com/svg.latex?q&space;=&space;1&space;-&space;p) is ![](https://latex.codecogs.com/svg.latex?0.01).
- The probability of success defined as when gasket would be functional, ![](https://latex.codecogs.com/svg.latex?p&space;=&space;0.99).
- The desired "success" defined as the replacement of a whole box, ![](https://latex.codecogs.com/svg.latex?P(x\geq2)&space;=&space;1&space;-&space;P(x&space;<&space;2)).

Plugging in the numbers and I'd get:

![](https://latex.codecogs.com/svg.latex?y%3Dx%5E2)

[back](./challenge.md)
