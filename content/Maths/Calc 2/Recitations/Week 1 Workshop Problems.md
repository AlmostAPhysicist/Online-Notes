
--- 
Aryan Malhotra
am4045

September 6, 2024

---
## Problem 1.

In the very first step of their answer, the student made a couple mistakes.
    $$\int_{1}^{4} \frac{1}{1+\sqrt{x}} \, dx = \int_{1}^{4} \frac{1}{u} \, du \tag{1}$$
Here, they directly substituted in $u$ and $du$ instead of relating $dx$ and $du$.
Furthermore, the student did not change the bounds of the integral ($1$ & $4$) for what they would have been in the $u$-space.

The correct way to do it would be:
$u = 1 + \sqrt{x}$
$\displaystyle \implies \frac{du}{dx} = \frac{1}{2 \sqrt{x}}$
$\displaystyle \implies dx = 2 \sqrt{x} \, du$

Now that we have a relation between $du$ & $dx$,
We can take a look at the bounds in $u$-space.
$x=1 \implies u=1+\sqrt{1}=2$
$x=4 \implies u=1+\sqrt{4}=3$

Hence, the integral $\displaystyle \int_{1}^{4} \frac{1}{1+\sqrt{x}} \, dx = \int_{2}^{3} \frac{1}{u} \, 2\sqrt{x} \,du$

$\displaystyle =\int_{2}^{3} \frac{2(u-1)}{u} \,du$
$\displaystyle =2\int_{2}^{3} \frac{(u-1)}{u} \,du$
$\displaystyle =2\int_{2}^{3} (\frac{u}{u} - \frac{1}{u})\,du$
$\displaystyle =2\int_{2}^{3} (1 - \frac{1}{u}) \,du$
$=2((u-\ln(u))\bigg|^3_2)$
$\displaystyle=2(1-\ln(\frac{3}{2}))$
$=2+\ln(\frac{4}{9})$

## Problem 2.
### (a)
$$\int^{\pi/24}_{0} \frac{(\sin(6x))^{3}}{1+\cos(6x)}\, dx$$
$u=1+\cos(6x)$
$\displaystyle \implies \frac{du}{dx}=-6\sin(6x)$
$\displaystyle \implies \frac{-du}{6}=\sin(6x)\,dx$

$x=0\implies u=1+1=2$
$\displaystyle x=\pi/24 \implies u=1+cos(\pi/4)=1 + \frac{1}{\sqrt{2}} = \frac{1+\sqrt{2}}{\sqrt{2}}$

The Integral can be written as $\displaystyle \int^{\pi/24}_{0} \frac{(\sin(6x))^{2}}{1+\cos(6x)}\, \sin(6x)\,dx$
$\displaystyle =\int^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2} \frac{1-cos(6x)^2}{u}\cdot \frac{-du}{6}$
$\displaystyle =\int^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2} \frac{1-(u-1)^2}{u}\cdot \frac{-du}{6}$
$\displaystyle =\int^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2} \frac{1-(u^2-2u+1)}{u}\cdot \frac{-du}{6}$
$\displaystyle =\int^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2} \frac{1-u^2+2u-1}{u}\cdot \frac{-du}{6}$
$\displaystyle =\frac{1}{6} \int^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2} (u-2)\,du$
$\displaystyle= \frac{1}{6}((\frac{u^2}{2}-2u)\bigg|^{\frac{1+\sqrt{2}}{\sqrt{2}}}_{2})$
$\displaystyle=\frac{1}{6} (\frac{3+2\sqrt{2}}{4} - \frac{2+2\sqrt{2}}{\sqrt{2}} -2)$

### (b)
$$\int x^{3} \sqrt[3]{x^2+1}\,dx$$
$u=x^2+1$
$\displaystyle \implies \frac{du}{dx}=2x \implies \frac{du}{2}=x\,dx$
Hence, the integral $=\displaystyle \int x^{2} \sqrt[3]{x^2+1}\,x\,dx$
$\displaystyle = \int (u-1) \cdot u^{\frac{1}{3}}\, \frac{du}{2}$
$\displaystyle = \frac{1}{6} \int u^{\frac{4}{3}}-u^{\frac{1}{3}} \, du$
$=\displaystyle \frac{1}{6}(\frac{3u^{\frac{7}{3}}}{7}- \frac{3u^{4/3}}{4})+c$
$=\displaystyle \frac{3}{14}(x^{2}+1)^{\frac{7}{3}} - \frac{3}{8}(x^2+1)^{\frac{4}{3}}+c$


### (c)
$$\int \frac{1}{\sqrt{6x-x^{2}}}\,dx$$
$\displaystyle = \int \frac{1}{\sqrt{-(x^{2}-6x)}}\,dx$
$\displaystyle = \int \frac{1}{\sqrt{-(x^{2}-6+9-9)}}\,dx$
$\displaystyle = \int \frac{1}{\sqrt{-((x-3)^2-9)}}\,dx$
$\displaystyle = \int \frac{1}{\sqrt{3^2-(x-3)^2}}\,dx$
$\text{let } u=x-3$
$du=dx$
$\displaystyle \therefore Integral= \int \frac{1}{\sqrt{3^{2}-u^{2}}}\, du$
$\displaystyle =\sin^{-1}(\frac{u}{3})+c$
$=\displaystyle \sin^{-1}(\frac{x-3}{3})+c$

### (d)
$$\int \frac{x^3+1}{x^2+4}$$
After Long division,

$\displaystyle= \int (\frac{1-4x}{x^{2}+4}+x)\,dx = \int \frac{1}{x^{2}+4} \, dx - \int \frac{4\,dx}{x^2+4}+\int x\,dx$

$\text{let }u=x^{2}+4$
$\implies \frac{du}{dx}= 2x$
$\displaystyle \therefore Integral= \frac{1}{2}\arctan\left(\frac{x}{2}\right)-2\ln(u)+\frac{x^2}{2}+c$
$\displaystyle \therefore Integral= \frac{1}{2}\arctan\left(\frac{x}{2}\right)-2\ln(x^2+4)+\frac{x^2}{2}+c$


## Problem 3.
### (a)
$$y=4-x^{2} \quad \& \quad y=4(1-x)=4-4x$$
![[Maths/Intro to Linear Algebra/attachments/Drawing 24-09-06-11-01-28|1000]]![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-07-01-40-12]]

I would argue it's easier to evaluate the integral (atleast by hand) w.r.t. $x$ since a polynomial function is much easier to deal with than the $\sqrt{\phantom{0}}$ function we would have to integrate otherwise.
Since there's only 2 piecewise integrals, it should be much nicer to evaluate that that to evaluate a tougher integral.

(2 easy integrals are better than 1 tough one.)

$$\int^{1}_{0}(4-x^2)-(4(1-x))\,dx+\int^{2}_{1}4-x^2\,dx$$
$$\int^{4}_{0}\sqrt{4-y} -(1- \frac{y}{4})\,dy$$
Evaluating the first limit:
$\displaystyle I= \int^{1}_{0}4x-x^2\,dx+\int^{2}_{1}4-x^2\,dx$
$\displaystyle I= (2x^2-\frac{x^3}{3})\bigg|^1_0+(4x-\frac{x^3}{3})\bigg|^2_1$

$\displaystyle I= 2 - \frac{1}{3} + 4 - \frac{7}{3}$
$I = 6-1=5$

### (b)
![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-06-11-27-08|1000]]
It would be easy to evaluate the integral w.r.t. x since both functions are fairly simple and it's just 1 integral to compute.

$$\int^{1}_{-1} \frac{4}{x+2}-(3-x)\,dx$$
$$\int^{4}_{1} | (\frac{4}{y}-2)-(3-y)|dy$$
Evaluating the first expression:
$I = (4ln|x+2|-3x+ x^\frac{2}{2})\bigg|^1_{-1}$
$=ln(81)-6$

### (c)
![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-06-11-41-06|1000]]

Integrating it w.r.t. x is obviously easy. It's just 2 integrals of polynomial functions.

Integrating w.r.t. y seems like a nightmare! As I would have to play with **3 functions!**
- the linear function
- 2 different branches of the inverse relation...
	- 1 branch to the right of the vertex
	- 1 branch to the left of the vertex

$$\int^{3}_{1}1-(x-2)^{2}\,dx + |\int^{3}_{0.5} \frac{x-3}{2}\, dx|+ \int^{1}_{0.5}1-(x-2)^{2}\,dx$$























