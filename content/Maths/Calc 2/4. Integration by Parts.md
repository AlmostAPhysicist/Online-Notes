Remember the Product rule?
$$\frac{d}{dx}(uv)=\frac{du}{dx}v+u\frac{dv}{dx}$$
Integration by parts is just this thing turned over its head.
$\displaystyle d(uv)=du\,v+u\,dv$
$\implies \displaystyle d(uv) - du\,v=u\,dv$
Integrating both sides,
$\implies \displaystyle \int d(uv) - \int du\,v=\int u\,dv = uv - \int du\,v$
That is it! That is integration by parts!
$$\int u\,dv = uv - \int du\,v$$


### Example 
$$\int x\,e^{2x}\,dx$$

| $u=x$   | $dv=e^{2x}\,dx$                       |
| ------- | ------------------------------------- |
| $du=dx$ | $\displaystyle v= \frac{1}{2} e^{2x}$ |
$\displaystyle \int u\,dv = uv - \int du\,v$
$\displaystyle\implies \int x\,e^{2x}\,dx = x \cdot \frac{1}{2} e^{2x} - \int \frac{1}{2} e^{2x}\,dx = x \cdot \frac{1}{2} e^{2x} - \frac{1}{4} e^{2x}+c$

---
# How to pick your $u$'s and $dv$'s?
- I (nverse Trig)
- L (ogarithms)
- P (polynomial)
- E (exponential)
- T (rignometric)

Essentially, things that are hard to let as $dv$ since you don't know their integral!
Or things that die off easily
Or something which has a derivative that cancels out with something else.

## Something out of Nothing 
$$\int ln(x)\,dx$$
$\displaystyle= \int 1\cdot ln(x)\,dx$


| $u=ln(x)$            | $dv=dx$             |
| -------------------- | ------------------- |
| $du=\frac{1}{x}\,dx$ | $\displaystyle v=x$ |
$\displaystyle= x\,ln(x) - \int x\cdot \frac{1}{x}\, dx$
$\displaystyle=x\,ln(x)-x+c$

---
![[Maths/Calc 2/attachments/Integration by Parts (1).jpg]]
![[Maths/Calc 2/attachments/Integration by Parts (2).jpg]]
