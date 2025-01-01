![[Maths/Calc 2/attachments/Drawing 24-09-05-05-19-57]]# Area Between Curves
$\displaystyle \int^{b}_{a} f(x) dx \implies$ signed area between the graph of $f(x)$ and the x-axis

---

Q: What is the area of the shaded region?

![[Maths/Calc 2/attachments/Drawing 24-09-04-06-00-25]]


Thinking about it, Area under curve $f(x)$ is the $\displaystyle \int^{b}_{a} f(x) dx$ and Area under curve $g(x)$ is the integral $\displaystyle \int^{b}_{a} g(x) dx$.
Hence, The area of the region is the difference between the two.

>If $f(x)$ & $g(x)$ are two functions defined on [a, b] and $f(x) \geq g(x)$ on [a, b], then the area of the region between f & g from x=a to x=b is $\displaystyle \int^{b}_{a} f(x) dx - \displaystyle \int^{b}_{a} g(x) dx = \displaystyle \int^{b}_{a} (f(x)-g(x) )dx$

Note: If we don't know which one is above the other, we might take $\displaystyle \int^{b}_{a} |f(x)-g(x)| dx$ as long as both $f(x)$ and $g(x)$ are positive and one stays strictly on top of the other.

Note... if they CROSS each other, we might have to break the function's intervals down into different sub-intervals.

#funfact 
The fact that $\displaystyle |\int^{b}_{a} f(x) dx| <= \displaystyle \int^{b}_{a} |f(x)| dx$
by the same reasoning as $|a+b| \leq |a|+|b|$ (kinda like stating that sum of 2 lengths of a triangle are greater than the third)

i.e. a & b can cancel each other out hence |a + b| will at max be |a| + |b|.

It is hence called the **Triangle Inequality**.


### Ex. 1.
Find the area of the region R bounded between curves $y=x^{2} \quad \& \quad y=2x+1$

```desmos-graph
y=x^2
y=2x+1
```
hence, the region between (R) would be Area under graph up top (green) take away the Area under graph at the bottom (blue) between their intersection points.

$x^{2}-2= 2x+1 \implies x=-1,3$
Hence, the area is $\displaystyle \int^{3}_{-1} (2x+1)-(x^2-2) dx$
$= \displaystyle \int^{b}_{a} (2x+3-x^2) dx$
$= \displaystyle x^{2}+ 3x + \frac{-1}{3}x^{3} | _{-1}^3$
$= 32/3$ 





$\frac{1}{2}$
```desmos-graph
y=x^2
```
