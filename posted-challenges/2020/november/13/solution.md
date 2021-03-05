---
layout: default
---

# solution

The wording was a bit unusual to me, but I believed that the point of the challenge was to find the probability of the company having to replace the package; two or more gaskets would have to be defective. 

![](images/binomial.png)

I defined a few things from the given information:

- The number of trials, **n**, is 20. That would be the number of gaskets in a box.
- The probability of failure defined as when gasket would be defective, **q = 1 - p** is 0.01.
- The probability of success defined as when gasket would be functional, **p** is 0.99.
- The desired "success" defined as the replacement of a whole box, **P(x >= 2) = 1 - P(x < 2)**.

Plugging in the numbers and I'd get:

<img src="http://www.sciweavers.org/tex2img.php?eq=P%28x%20%5Cgeq%202%29%20%3D%201%20-%20P%28x%3C2%29&bc=White&fc=Black&im=png&fs=12&ff=arev&edit=0" align="center" border="0" alt="P(x \geq 2) = 1 - P(x<2)" width="192" height="18" ></2>

[back](./challenge.md)
