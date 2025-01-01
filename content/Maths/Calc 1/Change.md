Now that we have some foundation for functions, let's look at something calculus is really about — How they **change**.

# Why look at change?
The Le Mans 24 Hours Race has about 370 laps of a roughly 13.5 kilometers (8.5 miles) long circuit, driven over 24 hours (as the name suggests).

Cool!

That's about 210 km/h maintained for 24 hours! 

While comparison is the thief of joy, it can give us some nice insights. 

For an average trip from New York to Washington DC, you'd be driving at an average of 80 km/h for 4.5 hours.

See?
Just giving you the distance and time might not be as insightful as giving you the **RATE** of traversing that distance.
And you can get an even better insight by comparing different rates!

That's what differential calculus is about — Comparing rates of change.
# Forward and Up
A function does this little dance based on the input value ($x$).
I.e. the values of the function $f(x)$ change based on the input $x$.

But what KIND of dance is this? HOW does the function change over its input?

A nice way to think of it is to see how the function $f(x)$ behaves for a particular increment in the input.
In other words,

> What is the Change in y for a particular Change in x

![[Maths/Calc 1/attachments/Drawing Linear function]]
See how you can kinda say "For each step forward, we can move a step up"?

That is literally what is happening.
This is a really nice way to see how the function changes with its input!
We can interpret the curve the be steadily increasing this way.

![[Maths/Calc 1/attachments/Drawing Quicker Change]]
But so is this one. This is also a steady increase. But a rather steep one! This one moves **2** steps up for each step forward!

![[Maths/Calc 1/attachments/Drawing Slower Change]]
This is yet another steadily changing function. This one goes 2 steps ahead for every 1 step up.

![[Maths/Calc 1/attachments/Drawing Comparing Quickness of Change]]

Here's all 3 of them together. It's obvious that the red one changes "Quickly", the green one changes "Slowly".

---
**Ahhh! That! That is what we're after. The sense of quickness and slowness of the change is exactly what calculus is about!**

---
You see, "1 step forward and 1 step up" these are 2 numbers. We want to somehow capture the essence in 1 quantity.
We need to DO something with these two numbers.
We can Divide them!

That is how we define change.
$$\frac{\text{Change in y}}{\text{Change in x}}$$
THAT is how we mathematically define the $Slope$ of a function.
It's a **RATE of Change**.
It almost completely captures the essence of how quickly the function is changing. 
A higher slope means the y value changes more quickly for the change in x value.
A lower slope, means the change is slow.

![[Maths/Calc 1/attachments/Drawing Comparing Quickness of Change|Drawing Comparing Quickness of Change]]

The blue one has a $slope = \frac{1}{1} =1$
The red one has a $slope = \frac{2}{1}=2$
The green one has a $slope = \frac{1}{2}= 0.5$ 
So the red one is the steepest slope, green one is the least steep slope. 

This nicely captures the essence of quickness of change.

![[Maths/Calc 1/attachments/Drawing Constant function]]
How about this one?

It has no change in y, so its slope is $0$. I.e. there is no change. No dance!

---
Slopes don't have to be constant, they can change!
![[Maths/Calc 1/attachments/Drawing Changing Slopes]]
These for instance have a different slope in the beginning and a different one in the end.

Ahaa! Change in the Rate of Change!

---
All right... before I get too ahead of myself.
Let's get this idea down in a more concrete way.

Change. 
You can only define change when you have a comparison.

And you need atleast 2 things for a comparison. So that is literally what we do.

We pick any two points on a function, look at how many steps up the function goes for the steps it went forward in between those two points.

![[Maths/Calc 1/attachments/Drawing Slope Depiction]]

That's it!


(The $\Delta$ (Delta) symbol you see is a #convention or a standard notation that means “Change”. So $\Delta y$ means Change in y)

This Change in y and Change in x fraction is also sometimes called $\frac{rise}{run}$ because... well... going up means to rise... and run is to go forward.
Simple.

So you can kinda get a sense of how quickly something changes within an interval with the slope for the interval's end points.
(Notice how a negative slope means the change is negative. That is, y is decreasing for an increase in x)

That line passing through the 2 points is called a $Secant$. It's essentially a linear approximation for that particular interval. (The line Segment is called a Chord)

**So the approximate change for a function over a particular interval can be thought of as the slope of the Secant line approximating that interval for its end points.**

---

It is however, only an approximation.
![[Maths/Calc 1/attachments/Drawing Slope Depiction|Drawing Slope Depiction]]

Notice how in reality, the function changes more quickly near point 1. It is only because it later decreases that the Average slope is lower.

# A better Approximation

If we want to get something closer to reality, we can try trimming down the interval, brining the 2 end points closer together to what we actually want.
![[Maths/Calc 1/attachments/Drawing Closer End points for Secant]]
Now That's a better approximation.
But it's still just an approximation. And it will always be!

![[Maths/Calc 1/attachments/Drawing Better Secant Approximates|1000]]
As long as the slope of the function is ever-changing, what lies within the end points of the function interval will never match with our secant line which has a constant slope. 

And thus, the secant will only be an approximation. And so will be the slope for the particular interval.

Notice however, the closer the intervals are, the better the approximation!

You might want to **practice** approximating curves with linear functions and finding slopes with [First Set of Khan Academy Calculus 1 Unit 2](https://www.khanacademy.org/math/calculus-1/cs1-derivatives-definition-and-basic-rules)
# Done with approximating — Derivatives

It kinda gives me an itch knowing that these are still just approximations.

What is EXACTLY the change at that point?

## Who cares if it isn't exact?
Duh... who cares! 

Well... Everyone does!

Say you have a Laser Distance Meter (just a tool to measure someone's distance from you by shooting off lasers and seeing when they bounce back)

And let's say Josh starts off with his car and travels further down a road while you stand there measuring his distance from you.

![[Maths/Calc 1/attachments/Drawing x-t graph]]

Say that is the distance that he notes for different times

![[Maths/Calc 1/attachments/Drawing x-t graph avg speed]]
He travels a total of 10km after 100s

So his speed $$s=\frac{d}{t}= \frac{10\space km}{100\space s}=100\space m/s$$
Notice, How this is exactly the slope from the origin to his final position in the graph.

YES! The Slope of an x-t graph gives us speed!

But it's just his average speed during his journey. Say you wanted to know his speed in the last 10 seconds... you'd find the slope :
![[Maths/Calc 1/attachments/Drawing x-t graph last 10s]]

So you'd say he travelled 2.5km in 10s, so his speed is $$s = \frac{2.5\space km}{10\space s}=250\space m/s$$
Still just an average or approximate speed for a particular interval. 

But say I want to know his speed AT the 90th second. Not his speed within some range. But just really how fast was he moving AT that instance?

I know, it's counter-intuitive. You can not define change for a particular point. But you can define the behavior of a function at and around a point!

How nice would it be could not just approximate but know exactly how the function changes at Point A!

Pushing this idea to its extreme, we CAN, in some sense, get the change at a particular point!

---
# The True spark of Differential Calculus
The problem is that the function curve within the end points doesn't ever fit exactly with the secant line since the curvature of the function is never constant as the secant.
It closely resembles the secant as we bring the two points closer together, but it's never quite there.

Except, what if the two points were really close!? Like REALLYYY Close!
So close that the distance between them was infinitesimally small and THERE WAS NO CURVE BETWEEN THE POINTS?
Like the points were it! Nothing in between the interval to compare!

Wait... but if there is nothing in between... the points literally sit on top of each other! It is a SINGLE point!

YES! What if we had that! What if we just made the points sit on top of each other!?

#important
Well then we would lose the very meaning of word “Change”

INDEED! But we wouldn't lose it as long as we're not yet there.
Hmmm... Remember [[Maths/Calc 1/Limits#^7e2752|x/x]]?
We had the same problem with $f(x)=\frac{x}{x}, \quad x=0$
the function seemed to be well defined for everything BUT $x=0$!

#emphasis
THIS IS WHY IT IS SO CRUCIAL TO PLAY WITH LIMITS BEFORE CALCULUS.

On its own, defining change for a single point has no meaning. But the idea of seeing what the change approaches for when the 2 limiting points of the secant get closer and closer together, to the point they become 1 single point... THAT exists! And THAT limit is the derivative of the function at that particular point.

Mathematically, and I hope you can now intuitively make sense of this...

$\text{Derivative of f at x, often denoted as }$
$$
f'(x) \space or \space \frac{dy}{dx} \text{(We'll see why in a bit...)} = \lim_{h\to0} \frac{f(x+h)-f(x)}{h}
$$

It is the value that the slope $\frac{\Delta y}{\Delta x} = \frac{y_2-y_1}{x_2-x_{1}}= \frac{f(x_2)-f(x_1)}{x_2-x_{1}} = \frac{f(x_{1} + \Delta x)-f(x_1)}{\Delta x}$ approaches for the change in x ($\Delta x$ or $h$ by #convention) getting closer and closer to $0$.

I.e. A derivative is the slope $\frac{\Delta y}{\Delta x}$ as the interval $\Delta x$ becomes smaller and the end points approach each other, eventually sitting on top of each other!

It is NOT the fraction when the denominator IS $0$. That is not defined and has no meaning. 

A derivative, (by definition!) is what the fraction **approaches** as the denominator gets closer and closer to zero. And in doing so, you actually do get the actual slope of not the secant, but now the TANGENT line for the function. A tangent being a line that only just *touches* a curve at a single point.

![[Maths/Calc 1/attachments/Drawing Closer End points for Secant|Drawing Closer End points for Secant]]
Since there is no function curve to fit, the tangent line we get by approaching the other secants for points closer and closer together truly mimics the slope AT the particular point.

The slope of the tangent is hence the slope of the curve AT that point.
This limiting fraction $\displaystyle \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x}$ is what is denoted by $\frac{dy}{dx}$. It's just the slope for a tangent of a curve.

There are different notations for this. That is because different people came about this idea — **Isaac Newton** and **Gottfried Leibniz** being the 2 major names for the “discovery” of this piece of mathematics.

Newton gave us the $\dot{y} \space \& \space y'$ notation. 
Leibniz took a more infinitesimal kinda approach and worked with the $\frac{dx}{dt}$ notation that has stuck around.

They all mean the same thing though... it's the limiting fraction $$\lim_{h\to0} \frac{f(x+h)-f(x)}{h}$$(Often called the First Principles since it's the very foundation of differential calculus) that just means the limiting ratio of the change in $y$ (numerator) and the change in $x$ (denominator). 

Literally the definition of slope we talked about — just the limiting ratio for a denominator approaching $0$.

# Computing Derivatives
We haven't yet discussed how to solve these limits though.
And it isn't really any different from the limits we've (hope you've practices a few) solved thus far!

Alright let's try one... what is the slope of the function $f(x)= y = x^2$ at $x=2$?

by the first principles, it's
$$\lim_{h\to0} \frac{f(x+h)-f(x)}{h}$$
$$=\lim_{h\to0} \frac{(x+h)^2-x^2}{h}$$
(remember how we would solve such limits? See if something cancels out!)
$$=\lim_{h\to0} \frac{x^2+h^2+2xh-x^2}{h}$$
$$=\lim_{h\to0} \frac{h^2+2xh}{h}$$
since both terms when separated would only be a polynomial function and would hence be continuous, the limit is validly defined for the two terms individually.
 $$=\lim_{h\to0} \frac{h^{2}}{h} + \lim_{h\to0} \frac{2hx}{h}$$
 $$=\lim_{h\to0} h + \lim_{h\to0} 2x$$
  $$=0 + 2x$$
  $$=2x$$
Hence, the slope at $x=2$ is $2\cdot2 = 4$


Now technically, this is it. But there's a lot more to derivatives. It is one of THE (if not THE) most useful tools in all of mathematics. You don't always have to use first principles. In fact, thanks to a few patterns that one can observe, there are certain tricks/rules for computing derivatives on the go.

To practice them, continue on with the rest of the sections of [Rest of the problems of Khan Academy Calculus 1 Unit 2](https://www.khanacademy.org/math/calculus-1/cs1-derivatives-definition-and-basic-rules)











