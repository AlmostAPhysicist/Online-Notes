The idea of Limits is very simple. It just takes a single word to descript it - **Approach**. 
It simply defines the value that some [[Maths/Calc 1/Number Wizardry - Relations and Functions#Function|function]] approaches as the input approaches some defined number.


---
Let's take a look at an example to understand things better. Take the function $f(x) = 2x$.
![[Maths/Calc 1/attachments/Drawing approach 2x|1000]]

$f(0.5)=1$
$f(0.9)=1.8$
$f(0.99)=1.98$
So you'd *expect* $f(1) = 2$

The value seems to **approach** $2$ for the input $x=1$

In mathematical terms, $$\lim_{x \to 1}f(x) = 2$$
This also happens to be what you would expect. Nice and easy.

---
# Do functions need to approach something?

What's $\frac{1}{0}$? 
Let's see… 
$\frac{1}{1}=1$
$\frac{1}{0.1}=10$
$\frac{1}{0.01}=100$
$\frac{1}{0.001}=1000$
$\frac{1}{0.0001}=10000$

The smaller the denominator gets, the larger the value.

This fact that this hints $\frac{1}{0}$ is something ENORMOUS is the very idea of Limits. The value seems to be **approaching** a very large value, the closer we get to $\frac{1}{0}$

So $\frac{1}{0}= \infty$ right?
Take a look at $f(x)=\frac{1}{x}$ for a while…
![[Maths/Calc 1/attachments/Drawing div by 0]]
So, again, what is  $\frac{1}{0}$? 
$-\infty$? $+\infty$? 
We can't pick one! The. We have to pick the ***direction of approach!*** Aha!

So **approaching** the input $x=0$ from the left gives us $-\infty$
And **approaching** the input $x=0$ from the right gives us $+\infty$

So Mathematically we say , $\displaystyle\lim_{x \to 0^{+}} \frac{1}{x}= +\infty$   but   $\displaystyle\lim_{x \to 0^{-}} \frac{1}{x}= -\infty$ 

{$0^{+}$ means approaching from the positive direction, $0^-$ means approaching from the negative direction}

Hmmm... so the function doesn't approach anything? 
Yes! It doesn't! 

$\displaystyle\lim_{x \to 0} \frac{1}{x}$ does not exist in general! 
(no $+ \enspace or \enspace -$ this time) 

That's intuitive! Right? The function, quite visually, approaches difference values for different directions.

We just proved that division by $0$ can not be assigned a value!

> $\frac{a}{0}$ is not defined!

^c8df88

---
## A better example

To really see the distinction between the value and the limit, let's take a another case where the value isn't defined.

Say, $f(x)=\frac{x}{x}$. Nice and easy eh? ^7e2752

It's just 1. The *x*'s cancel out, and the function is just a constant.
And you'd be right! 

Except… when you input $x=0$.

The truth is, the value of the function doesn't exist for that input.
It really doesn't.
$\frac{0}{0}$ holds no value. 

Division by zero isn't allowed remember? We just proved it!

>$\frac{a}{0}$ isn't defined, 

hence $\frac{0}{0}$ isn't either.

So, 
for $f(x)=\frac{x}{x}$, $\quad f(0)\neq1$
yet, $$\lim_{x\to0}f(x)=1$$
![[Maths/Calc 1/attachments/Drawing hole in func]]
See why? 

It's because the function approaches the value $1$. You can almost See it! Right?

No matter how arbitrarily close you approach $0$ as an input, as long as you aren't there, you can divide without any issues. 
The function is indeed valued $1$ for all inputs.

But as soon as you get to $x=0$, You divide by zero! Not cool!
Hence, the limit holds true! Yet, the function itself has a hole.

$f(x) = \frac{x}{x}$ is discontinuous at $x=0$, whereas $f(x)=2x$ is continuous for all values of x.

The ***Limit*** for both of these however, exists.
Kind of like saying both $2x$ and $\frac{x}{x}$ "feel" to have a continuous nature. Yet the latter doesn't truly have it.

Think of the limit as something you “feel” should be correct.

Notice how it's different from the $\frac{1}{x}$ example? For $\frac{x}{x}$ it feels almost right to say the value must be 1 because both directions approach the same thing!

---

We formally call these ***Left Hand Limit*** ($a^-$) and the ***Right Hand Limit*** ($a^+$)
or LHL and RHL for short.

Mathematically,
When LHS = RHS, the limit of the function exists. i.e.
$$\displaystyle\lim_{x \to a^{-}} f(x) = \lim_{x \to a^{+}} f(x) \implies \exists \space \lim_{x \to a} f(x)$$

Furthermore, we can say if
$$\displaystyle\lim_{x \to a^{-}} f(x) = \lim_{x \to a^{+}} f(x) = f(a)$$
i.e. if both one-sided limits approach the value of the function, the function is Continuous at that point!

Woah!!!
That is a lottt to take!

---
Let's look at the examples that we talked about.
$$\displaystyle\lim_{x \to 1^{-}} 2x = \lim_{x \to 1^{+}} 2x = 2 = f(x) \enspace\text{ for  }\enspace f(x) = 2x$$
therefore, since the value and the limits for the function $f(x)=2x$ both approach the same value, ***the function is Continuous*** at $x=1$.


$$\displaystyle\lim_{x \to 0^{-}} \frac{x}{x} = \lim_{x \to 0^{+}} \frac{x}{x} = 1 \quad \neq \quad undefined =\frac{0}{0} = f(x) \quad \text{ for  }\enspace f(x) = \frac{x}{x}$$
Again, since we proved [[#^c8df88| division by zero is not defined]], $\frac{0}{0}$ is not either. Hence, $\frac{0}{0}=undefined \neq 1$

therefore, since the value of the function $\displaystyle f(0) \neq \lim_{x \to 0} f(x)$, ***this function is Discontinuous***.

> As a general rule of thumb, any time a function has a potential $0$ in the denominator, it is discontinuous; the point of discontinuity would be the input value at which the denominator became 0
> 
> Example:
> $f(x) = \frac{1}{(x+1)(x-1)}$ is discontinuous at $x=-1,1$



---

**If** however, we define the function explicitly at the point of an otherwise discontinuity, we can **Patch** the hole that caused the discontinuity!
$$
f(x) = \begin{cases}
  1, & \text{if } x = 0 \\
  \frac{x}{x}, & \text{if } x \neq 0
\end{cases}
$$
would thus be a Continuous function!

This case-wise definition helps us maintain continuity.

Nice work!

---

# Practice and Computing Limits
Test yourself out with [Khan Academy's Unit 1 for Calc 1](https://www.khanacademy.org/math/calculus-1/cs1-limits-and-continuity) exercise questions.

A nice question I found was something along the lines

![[Maths/Calc 1/attachments/Drawing Jump Discontinuity 2]]![[Maths/Calc 1/attachments/Drawing Jump Discontinuity 1]]
Find $\displaystyle \lim_{x\to2} (f(x)+g(x))$.

Now even though it's obvious that the limit doesn't exist for $f(x)$ and g(x) individually for point $x=2$, their combination can indeed have a valid limit.
![[Maths/Calc 1/attachments/Drawing Combined discontinuous functions]]
Notice how when combined, $f(x) + g(x)$ would be nothing but sum of 2 continuous functions. Hence together, they can have a validly continuous function for all values of x.

![[Maths/Calc 1/attachments/Strategies for finding Limits.png]]
Finally, we can apply the L'Hôpital's Rule (more on that later) once we know how to differentiate things — the holy grail!

## Indeterminate Forms

$$\frac{0}{0}$$
$$\frac{\infty}{\infty}$$
$$0 \cdot \infty$$
$$0^0$$
$$\infty^0$$
There's more than 1 indeterminate forms. Usually, the trick is to either convert 1 into the other, rationalize, factor out, use some identities, use L'Hopital's rule, converting the function into an exponential function