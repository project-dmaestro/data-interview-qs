---
layout: default
---

# solution

The wording was a bit unusual to me, but I believed that the point of the challenge was to find the probability of the company having to replace the package; two or more gaskets would have to be defective. 

![](images/binomial.png)

I defined a few things from the given information:

- The number of trials ![](https://latex.codecogs.com/svg.latex?\inline&space;n) is 20. That would be the number of gaskets in a box.
- The probability of failure defined as when gasket would be defective, ![](https://latex.codecogs.com/svg.latex?\inline&space;q&space;=&space;1&space;-&space;p) is ![](https://latex.codecogs.com/svg.latex?\inline&space;0.01).
- The probability of success defined as when gasket would be functional, ![](https://latex.codecogs.com/svg.latex?\inline&space;p&space;=&space;0.99).
- The desired "success" defined as the replacement of a whole box, ![](https://latex.codecogs.com/svg.latex?\inline&space;P(x\geq2)&space;=&space;1&space;-&space;P(x&space;<&space;2)).

Plugged in the numbers and I'd get:

![](https://latex.codecogs.com/svg.latex?P(x&space;\geq&space;2)&space;=&space;1&space;-&space;P(x&space;<&space;2)) <br>
![](https://latex.codecogs.com/svg.latex?P(x&space;\geq&space;2)&space;=&space;1&space;-&space;P(x&space;=&space;0)&space;-&space;P(x&space;=&space;1)) <br>
![](https://latex.codecogs.com/svg.latex?P(x&space;\geq&space;2)&space;=&space;1&space;-&space;\frac{20!}{(20-0)!0!}&space;0.99^{0}&space;0.01^{20-0}&space;-&space;\frac{20!}{(20-1)!1!}&space;0.99^{1}&space;0.01^{20-1}) <br>
![](https://latex.codecogs.com/svg.latex?P(x\geq&space;2)&space;=&space;1&space;-&space;1.0e^{-40}&space;-&space;1.98e^{-37}) <br>
|[](https://latex.codecogs.com/svg.latex?P(x\geq&space;2)&space;\sim&space;1)

[back](./challenge.md)
