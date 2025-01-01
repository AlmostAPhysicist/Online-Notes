	#def Sequences : Ordered list of numbers

^b8564d

There doesn't HAVE to be a relation between numbers, but we can think of possible patterns.

Infinite Sequences:
The orders that keep going on forever 🫠.

Exercise:
- $2,\frac{1}{2},\frac{2}{9},\frac{2}{16} \dots$
	- just $a_n=\frac{2}{n^{2}}\enspace , n \in \mathbb{N}$

- $1,2,6,24,120 \dots$
	- just $a_n=n!$

- $\frac{-2}{3}, \frac{4}{9}, \frac{-6}{27}, \frac{8}{81}\dots$
	- $a_{n} = \frac{(-1)^{n} \cdot 2n}{3^{n}}$

- $2,3,5,7,11,13,17 \dots$
	- $a_{n} = \text{nth prime number}$

- $1,11,21,1211,111221$
	- #funfact this is called look and say
	- "one 1" -> 11
	- "2 ones" -> 21
	- "1 two and 1 one" -> 1211
	- ...
	- Conway proved this sequence spans forever and only contains ones, twos and threes 

- $2,7,1,8,2,8,4,5 \dots$
	- digits of $e$ (Euler's number)
	- Bummer!
		- But people do study this!

- Sequences can be defined piecewise!

They are just functions from the $\mathbb{N} \to \mathbb{R}$.
like $a_{n}$ maps to some Real Number.

(Intro to Real Analysis... deals with just all these number patterns)

---
The main interest of sequences for us is their behavior as we progress through the terms.

#def We say a sequence $a_{n}$ converges to a number $L$ if "$a_n$ gets arbitrarily close to $L$ as $n$ goes to $\infty$".
$$\lim_{n \to \infty} a_{n} = L$$
(More formally,
$\forall \enspace \epsilon > 0, \exists \enspace N: \text{if } n \geq N, \text{then } |a_{n}-L|<\epsilon$ )

#theorem If $a_{n} = f(n)$ & $f(x)$ is continuous, and the $\lim_{x \to \infty} f(x)$ exists or is $\pm \infty$, then $\lim_{n \to \infty} a_{n} = \lim_{x \to \infty} f(x)$

Basically, if there is a function $f(x)$ defined for all real numbers that encapsulates the series $a_{n}$ for all natural numbers $n$, then the limiting value as inputs for both the function and the sequence tend to the same value.

---
## Example 
- $\lim_{n \to \infty} \frac{3+n}{4+n+n^{2}}= 0$
	- since $\lim_{x \to \infty} f(x) = 0$
- $\lim_{x \to \infty} \frac{x^{77}}{e^{x}} = 0$
	- again, $e^{x}$ grows faster so the function's limit tends to Zero and hence so does that of the sequence.
- $\lim_{n \to \infty} (-1)^n$ diverges since it doesn't converge to a single output even if it oscillates between two finite numbers 
	- Note:
		- Convergence is defined only if the number settles to 1 specific finite value.
	- You can NOT tackle this with a functional approach since the function $(-1)^x$ is NOT real valued.
- $\lim_{n \to \infty} sin(\pi n) = 0$ since $sin(\pi n)$ is $0$ for any value of $n$.
- $\lim_{n \to \infty} \frac{e^{n}}{n!}=0$ since $factorials$ grows faster than $exponentials$
	- $\displaystyle \frac{e \cdot e \cdot e \cdot e \cdot e \cdot e \cdot \dots}{1 \cdot 2 \cdot 3 \cdot 4 \cdot 5 \cdot 6 \dots} = 0$ since the denominator terms tend to be ever larger than those of the numerator as $n \to \infty$.
	- You multiply ever decreasing fractions.

>A lot of limits boil down to comparing growth rates

### General Growth Rate Hierarchy 
- $ln(n)^a$ Powers of natural logs
- $n^{b}$ Polynomials 
- $c^{n}$ ($c>1$) Exponentials
- $n!$ Factorials
- $n^{n}$ Hyper Operated 

**As a consequence, if something grows faster, its reciprocal decays faster.**
### Useful Limits
$\displaystyle \lim_{n \to \infty} (1+ \frac{a}{n})^{bn} = e^{ab}$
$\displaystyle \lim_{n \to \infty} n^{\frac{1}{n}} = 1$ 
- or actually, since exponential functions grow faster, the decay rate of $1/n$ as a power is also higher than the growth rate of $ln(n)^a$ and $n^{b}$ and hence any of those raised to $\frac{1}{n}$ have a Exponential that is decaying very quickly and hence approaches $n^{0}=1$

Decay rates are confusing but powerful!

### Some Important Sequences and Definitions 
- A **Geometric Sequence**
	- is a sequence where $a_{n} = cr^{n}$, where $c$ and $r$ are constants ($r \neq 1$ for this course is not considered)
	- Example:
		- $b_{n}=3(\frac{-1}{2})^n$ diverges
	- $\displaystyle \lim_{n \to \infty} cr^{n} = \cases{0, \text{ if } |r| \leq 1\\ \text{diverges if |r| > 1 or r = -1}} \\ \quad \text{c, if r=1}$ 

### Recursive Sequences 
When a sequence is defined by it's previous terms
When you DEFINE a function by recursion (it might still have a normal functional way to write it)
- $a_{n} = a_{n-1} + a_{n+2}$, $a_1=a_2=1$ 
	- Fibonacci Sequence!
		- $\displaystyle a_{n} = (\frac{1}{\sqrt{5}})(\frac{1+\sqrt{5}}{2})^{n} - (\frac{1}{\sqrt{5}})(\frac{1-\sqrt{5}}{2})^{n}$

### Definitions 
#def A sequence $a_{n}$ has a **lower bound** (resp upper bound) if $m \leq a_{n}$ for all $n$ 
- A sequence is **bounded below** if it has a lower bound and all terms are $\geq$ that bound
- A sequence is **bounded above** if it has an upper bound and all terms are $\leq$ that bound
- A sequence is **bounded** if it has both an upper and lower bound
- A sequence is **unbounded** if it doesn't have at least one of bounds

- A sequence is **increasing** if $a_{n} \leq a_{n+1}$ for all $n$
- A sequence is **increasing** if $a_{n} \geq a_{n+1}$ for all $n$
- A sequence is **monotonic** if it is **either increasing or decreasing**
- Note how there is an Equality!
	- So depending on your definitions, you can have increasing include equality and hence consider constant functions to increase as well
	- More rigorously, if there is no equality, you call the behavior **Strictly Increasing or Decreasing**

#theorem Monotonic Convergence Theorem 
Every bounded Monotonic Sequence converges.

(Note how not all converging sequences are monotonic, but bounded monotonic sequences are for sure converging since if there are bounds above and below and is monotonic, all values are certainly finite.
eg: $b_{n} = (\frac{-1}{2})^{n}$ converges but is not monotonic (but is bounded). It oscillates but in the limit, settles to 1 number)

#cheesy The reason not all bounded sequences converge is that Divergence can occur because things can oscillate for Non-Monotonic functions!
	For instance, $a_{n} = (-1)^{n}$ is bounded but still diverging.

No sequence is monotonic, unbounded and converges