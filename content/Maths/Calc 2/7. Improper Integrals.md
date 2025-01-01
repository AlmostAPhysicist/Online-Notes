**Not Indefinite Integrals!**

>Integrals for which the region of integration is unbounded

#def If an integral has an infinite upper and/or lower bound (bounds extending to either $+ \infty$ or $- \infty$) then we say that the integral is an improper integral (Type 1)

- If $f(x)$ is continuous on $[a, \infty)$, then $$\displaystyle \int^{\infty}_{a} f(x)\,dx = \lim_{b \to \infty} \int^{b}_{a} f(x)\,dx$$
	- Note how it would otherwise not make sense but functionally, it is key to have the limit exist.
- Or for that matter, for any bound tending to a non-finite number, you need to take the limit of the bounds going off to the non-finite number and evaluate the integral for the bounds.
	- For both sides being non-finitely bound, you break the integral from one bound to a finite number and then continue from there on to the other bound.
	- $$\int^{\infty}_{- \infty}f(x)\, dx = \lim_{b_{1}\to -\infty} \int^{c}_{b_1} f(x)\,dx +\lim_{b_{2}\to \infty} \int^{b_2}_{c} f(x)\,dx$$
	- $\displaystyle \int^{\infty}_{- \infty}f(x)\, dx$ does NOT always equal to $\displaystyle \lim_{c \to \infty} \int^{c}_{-c} dx$ (maybe) because infinities can be approached in different ways and for limits to exist, you must do it from all possible ways. 
		- I think of it as there are different infinities and $c$ only means 1 particular infinity.
	- #funfact This is called the Cauchy Principal Value (CPV) as is a fun thing to think about
		- an even more amazing #funfact is that in Physics, We do consider the value of the function to be equal to CPV for many of the functions.
		- This is another one of those mathematically rigorous definitions that mathematicians Care too much about (maybe?).

>If these limits exist, and are finite, we say that the improper integral converges to the limit value, and if any of the limits fail to exist, then the integral diverges.

### Example 
$\displaystyle \int_{4}^{\infty} \frac{1}{\sqrt{x}} \, dx$
$\displaystyle = \lim_{b \to \infty}\int_{4}^{b} \frac{1}{\sqrt{x}} \, dx$
$\displaystyle = \lim_{b \to \infty} 2x^{\frac{1}{2}} |^b_4$ 
$\displaystyle = \lim_{b \to \infty} 2 \sqrt{b}-4 = \infty$

Since the limit blows up to infinity, the integral diverges!

$\displaystyle \int^{1}_{-\infty} xe^x\,dx$
$\displaystyle =\lim_{b \to -\infty} \int^{1}_{b} xe^{x}\,dx$
$\displaystyle =\lim_{b \to -\infty} (xe^{x} - e^{x})|^1_b$
$\displaystyle 0 - \lim_{b \to - \infty} be^{b}-e^{b}= 0$

Since the limit converges, the value of the integral IS $0$ (Zero).
$\displaystyle \int^{\infty}_{-\infty} \frac{1}{x^2+1}$
$\displaystyle= 2\int^{\infty}_{0} \frac{1}{x^2+1}\,dx$
$\displaystyle = 2 \lim_{b \to \infty} \int^{b}_{0} \frac{1}{x^2+1}\,dx$
$=\displaystyle 2 \lim_{b \to \infty} \arctan(b)-\arctan(0)$
$=\displaystyle 2 \lim_{b \to \infty} \arctan(b) = 2 \cdot \frac{\pi}{2} = \pi$


nice question here is
Find all values of p for which the function $\int^{\infty}_{a} \frac{1}{x(lnx)^{p}} \, dx$ converges

---
#def If $f(x)$ is continuous on $(a,b]$ and $f(x)$ has a Vertical asymptote at $x=a$ then $\int^{b}_{a} f(x)\,dx$ is improper (of type 2), and $$\int^{b}_{a} f(x)\,dx = \lim_{t\to a^{+}}  \int^{b}_{t} f(x)\,dx$$
If Vertical Axis occurs at $x=b$ instead, then $$\int^{b}_{a} f(x)\,dx = \lim_{t \to b^{-}} \int^{t}_{a} f(x)\,dx$$
I.e. limit for whatever side the integral approaches the bound value

If instead, the Asymptote occurs in between the interval, you break the interval and want to approach it from both sides in 2 different integrals

$$\int^{b}_{a} f(x)\,dx = \int^{c}_{a} f(x)\,dx+\int^{b}_{c} f(x)\,dx = \lim_{t \to c-}\int^{t}_{a} f(x)\,dx+\lim_{s \to c^+}\int^{b}_{s} f(x)\,dx$$
for an asymptote at $x=c$

---
#### Example 
$\displaystyle \int^{1}_{0} \frac{1}{\sqrt{x}}\,dx$
$\displaystyle = \lim_{t \to 0^{+}}2\sqrt{x}|^1_t=\lim_{t\to0^+}2-2\sqrt{t}=2$

---
## Divergence Tests
#theorem Direct Comparison Test 
Suppose $0 \leq g(x) \leq f(x)$ on $[a, \infty)$ & f(x) and g(x) are integrable on $[a, \infty]$.
Then 
- if $\int^{\infty}_{a} f(x)\,dx$ converges, so does $\int^{\infty}_{a} g(x)\,dx$.
- if $\int^{\infty}_{a} g(x)\,dx$ , so does $\int^{\infty}_{a} f(x)\,dx$.
- ![[Maths/Calc 2/attachments/Drawing 24-10-09-06-44-51]]
- ![[Maths/Calc 2/attachments/Drawing 24-10-09-06-46-04]]
- ![[Maths/Calc 2/attachments/Drawing 24-10-09-06-46-45]]

The Idea is, if $|g(x)|< |f(x)|$ then the area of $f(x)$ encapsulates that of $g(x)$ so if the boundary is finite, the thing inside must be finite. If the thing inside is infinite, the boundary must be so too.

### example
$$\int^{\infty}_{12} \frac{sin^2(e^{x^2})}{\sqrt{x^3+1}}\,dx$$
Since $sin^{2}(x)\leq 1$, the numerator is contained and since $$\int^{\infty}_{12} \frac{1}{\sqrt{x^3+1}}\,dx$$ converges, the initial function does so too!