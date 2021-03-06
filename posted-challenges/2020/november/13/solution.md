---
layout: default
---

# solution

![](images/binomial.png)

I defined a few things from the given information:

- The number of trials ![](https://latex.codecogs.com/svg.latex?\inline&space;n) is 20. That would be the number of gaskets in a box.
- The probability of success defined as when gasket would be defective, ![](https://latex.codecogs.com/svg.latex?\inline&space;p) is ![](https://latex.codecogs.com/svg.latex?\inline&space;0.01).
- The probability of failure defined as when gasket would be functional, ![](https://latex.codecogs.com/svg.latex?\inline&space;q&space;=&space;1&space;-&space;0.99).
- The desired "success" defined as the replacement of a whole box, ![](https://latex.codecogs.com/svg.latex?\inline&space;P(x\geq2)&space;=&space;1&space;-&space;P(x&space;<&space;2)).

Plugged in the numbers and I'd get:

![](https://latex.codecogs.com/svg.latex?P(x&space;\geq&space;19)&space;=&space;1&space;-&space;P(x&space;<&space;19)) <br><br>
![](https://latex.codecogs.com/svg.latex?P(x&space;\geq&space;19)&space;=&space;P(x&space;=&space;1)&space;-&space;P(x&space;=&space;2)&space;-&space;P(x&space;=&space;3)&space;-&space;P(x&space;=&space;4)&space;-&space;P(x&space;=&space;5)&space;-&space;P(x&space;=&space;6)&space;-&space;P(x&space;=&space;7)&space;-&space;P(x&space;=&space;8)&space;-&space;P(x&space;=&space;9)&space;-&space;P(x&space;=&space;10)&space;-&space;P(x&space;=&space;11)&space;-&space;P(x&space;=&space;12)&space;-&space;P(x&space;=&space;13)&space;-&space;P(x&space;=&space;14)&space;-&space;P(x&space;=&space;15)&space;-&space;P(x&space;=&space;16)&space;-&space;P(x&space;=&space;17)&space;-&space;P(x&space;=&space;18)) <br><br>
![](https://latex.codecogs.com/svg.latex?P(x\geq&space;19)&space;\sim&space;0.983141)

That'd meant about 1.68%

[back](./challenge.md)
