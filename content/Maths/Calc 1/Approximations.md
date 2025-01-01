[This video](https://youtu.be/3d6DsjIBzJ4?si=pLeZnuFVNvP8TJmJ) on Taylor series by 3B1B is in my opinion the best way to learn about approximations. 

Go give it a watch.
Let me give you my interpretation of it and how I were to explain this concept of approximating functions.

Say you have this function, any function $f(x)$.
You can always have another function $g(x)$ that, for a particular interval, looks alike.

```desmos-graph
left=-3; right=3;
bottom=-1; top=1.5;
---
    y = e^{-(x^2)}
```
Hmmm... It kinda curves downwards at near origin.
We can say it kinda looks like a $cos(x)$ curve near $x=0$.
```desmos-graph
left=-3; right=3;
bottom=-1; top=1.5;
---
    y = e^{-(x^2)}
    y = \cos{x}
```
Which it does!

Or maybe the curve is more like an upside down quadratic
```desmos-graph
left=-3; right=3;
bottom=-1; top=1.5;
---
    y = e^{-(x^2)}
    y = 1-x^2
```
Ahaa! That fits well!

$y=1-x^2$ is a pretty good approximation. It is almost an identical curve up until $x=0.2$.

Let's explore what makes a function a good candidate for an approximation.

# Characteristics of a nice fit
If anything, approximating a function $f(x)$ around $x=0$, the approximation function $g(x)$ must match the value $f(x)$ evaluated at $x=0$

I mean, $g(0) = f(0)$ must be an obvious starting point. We can then see how the function aligns nicely with other points.

Given that both have the same value at $x=0$, they would surely be the same if they change the same way from there on. 
$$g(0)=f(0) \qquad \textemdash \space eq. 1$$
So if after 2 steps forward, $f(x)$ goes down 1 step, $g(x)$ must also do the same thing right?

And what do we know about the [[Maths/Calc 1/Change|change]]? YES! The derivative!

If the slope of both $f$ and $g$ are the same, they change in the same way. Meaning, they will have the same value.

Now, We can see that at $x=0$, the tangent line is flat. So both functions must have a critical point there.

Hence, both must thus have the same slope at $x=0$

$$g'(0)=f'(0) \qquad \textemdash \space eq. 2$$

But really, How does the slope change? Is the slope increasing or decreasing?

In other words, What way does the function **curve** towards? What's the [[Maths/Calc 1/Curvature|Curvature]] of the function like?
(The 2nd derivative attributes to the curvature...)

>And upward curve would have the slope increasing. Hence a +ve 2nd Derivative would mean an upward curve while a -ve 2nd derivative would mean a downward curve.

>Note: the place where 2 curvatures intersect is an inflection point.
>This is where the slope is not changing near a particular value.

in other words, 

$$g''(0)=f''(0) \qquad \textemdash \space eq. 3$$
---

# Let's Recall

So we want 
$$g(0)=f(0)$$
$$g'(0)=f'(0)$$
$$g''(0)=f''(0)$$
Hmmm... That makes sense!
If we want the curves to fit and approximate one another, THEY MUST BEHAVE IN THE SAME WAY!

THEY **MUST** have the same properties and give same answers for mathematical operators.

>THE BEST APPROXIMATION FOR SOME VALUE $a$ WOULD BE $a$ ITSELF!

It's as simple as that!
So we can then say functions must gave the values of their nth derivatives at point $a$ to be the same if we want them to fir around the point $a$, and hope that this nice fit extends to infinity (It often does not!)

$$g'''^{\dots n}(a)=f'''^{\dots n}(a) \quad \forall \space n \space \epsilon \space \mathbb{Z}$$
would mean both functions are literally the same

That's it!
That, in my opinion should be the way to look at function approximation.

# Taylor series

If you've understood the above reasoning, understanding Taylor series is simple.

It's just the same idea but for a specific case of approximating functions with Polynomials.

Why would anyone do that?

Polynomials are nice! Easy to compute, easy to differentiate, integrate, just overall nice to work with!

# Example
So...
Let's say you want to approximate $sin(x)$ with Polynomials around $x=0$
```desmos-graph
right=7; left=-7;
top=1.5; bottom=-1.5;
---
y=\sin{x}
```

say the polynomial looks like 
$P(x)=c_{1}+c_{2}x+c_{3}x^{2}+c_{4}x^{3}\dots$
we know $P(0)=sin(0)=0$
$\implies c_{1}+c_{2}(0)+c_{3}(0)^{2}+c_{4}(0)^{3}\dots = 0$
$\implies c_{1}+ 0 = 0$
$\implies c_1=0$
Which is obvious! The constant is 0.

Now we want the next behaviour... slope to be the same

$P'(0)=sin'(0)=cos(0)=1$
$\implies 0+c_{2}+2c_{3}(x)^{1}+3c_{4}(x)^{2}\dots = 1 \quad \{P'(x)=1\}$
$\implies 0+c_{2}+2c_{3}(0)^{1}+3c_{4}(0)^{2}\dots = 1 \quad \{x=0\}$
$\implies c_{2}+ 0 = 1$
$\implies c_2=1$

Next up, the curvature or the 2nd derivative evaluated at $x=0$ must be the same

$P''(0)=sin''(0)=cos'(0)=-sin(0)=0$
$\implies 0+0+2c_{3}+6c_{4}(x)^{1}\dots = 1 \quad \{P''(x)=0\}$
$\implies 0+0+2c_{3}+6c_{4}(0)^{1}\dots = 1 \quad \{x=0\}$
$\implies 2c_{3}+ 0 = 0$
$\implies c_3=0$

and you get the idea.
NOTE it is NOT alternating between 0 and 1!

Look at the next one...

$P'''(0)=sin'''(0)=cos''(0)=-sin'(0)=-cos(0)=-1$
$\implies 0+0+0+6c_{4} + 24c_{5}x\dots = -1 \quad \{P'''(x)=-1\}$
$\implies 0+0+0+6c_{4}+ 0\dots = -1 \quad \{x=0\}$
$\implies 6c_{4}+ 0 = -1$
$\implies c_{4}= \frac{-1}{6}$

So our polynomial looks like 
$P(x)=0+1x+0x^{2}- \frac{1}{6}x^{3}\dots$
let's see if that is the case

```desmos-graph
right=7; left=-7;
top=1.5; bottom=-1.5;
---
y=\sin{x}
y=0+1x+0x^{2} - \frac{1}{6}x^{3}
```
Indeed it is!

In fact, if you keep doing this, you will get exactly the curve of $sin(x)$.

# Noticing the Pattern — Generalizing Taylor Series
In general, for every derivative we take, each term gets it's $x$ term's exponent multiplied up front, and power reduced (Standard Power rule) and each time we do this, we equate the value of the derivatives of the function at that point.

That gives us the constant term for $x^n$ for $nth$ derivative since the other terms are either $0$ or equate to $0$ because other terms still have an $x$ in them.

So we say the function
$P(x) = f(a) + f'(a)\frac{x-a}{1} + f''(a) \frac{(x-a)^{2}}{1\cdot2}+ f'''(a) \frac{(x-a)^{3}}{1\cdot2\cdot3}\dots$
Notice, it isn't simply $x$ but $x-a$ because we want the other terms to be 0.

This was not noticeable since we currently just worked with 0. But an obvious way to see this is to consider function shifted with X-axis shifted from $0$ to $a$.

Hence, In general, Taylor series gives us a polynomial approximation of a function around point $a$ by

$\sum^{\infty}_{n=0} f'''^{...n}(a) \frac{(x-a)^{n}}{n!}$

We were dealing with a nicer version of this... the MacLaurin series where a is nicely equal to 0.

But Taylor series is a more general way of approximating since you don't have to be stuck approximating values near $x=0$. It is nothing much that $x=0$ shifted to $x=a$ hence turning $0 \to a$
so $x-0 \to x-a \quad(\text{i.e. Unshifted Origin to Shifted Origin})$

