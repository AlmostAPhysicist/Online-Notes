
Know how a(t), v(t) and x(t) relate to each other as their integrals/derivatives?

Yeah that's fun...

Just know..
And Average Velocity = Total Distance/ Total time


Hence, Avg Value of the function = Integral of the function over some integral/ Length of the interval


Mathematically, let $f(x)$ be a function that is continuous for interval $[a, b]$. Then, the $Avg$ value of $f(x)$ for the interval is:
$$Avg(f(x))=\frac{\int^{b}_{a} f(x)\, dx}{b-a}$$

## Tricks to compute:
- Exploit Symmetries 
	- Even: f(x) is symmetric across the y-axis ($f(x)=f(-x)$ for all x)
		- ![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-09-05-58-45]]
		- Ex): cos(x), $x^{even\space power}$, |x|, sum(even functions), sum(odd functions)
		- For symmetric intervals about y-axis, areas repeat by symmetry $\int^{a}_{-a} evenfunction(x)\, dx=2\int^{a}_{0} evenfunction(x)\, dx$
		- 
	- Odd: f(x) is symmetric over the origin (the y=x diagonal, i.e. spinning around 180 degrees.) ($f(x)=-f(-x)$)
		- ![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-09-05-59-48]]
		- Ex): sin(x), tan(x), $x^{odd\space power}$, |x|, sum(even + odd function), sum(odd functions), inverse of odd functions -> *if you are reflecting about the origin, being already symmetrical wouldn't change anything!*
		- For the symmetric intervals about y-axis, areas cancel out. $\int^{a}_{-a} oddfunction(x)\, dx=0 \quad \{\text{a is finite}\}$
		- odd $\times$ odd = even
	- Not everything is suppose to be odd!
	- $f(x)=0$ is BOTH!

## Applications
- Geometry: Areas and Volumes
- Kinematics
- ANYTHING actually... ANYTHING that has to be summed over a functional change!

## Volume By Slicing (Washer Method)

![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-09-06-26-57]]


# Problem 3
Find the volume of the solid whose cross sections perpendicular to the x-axis are the semi circles whose diameter runs between x-axis and $y=\sqrt{sin(x)}$, $0\leq x\leq pi$

Essentially, $y=diameter$
each cross section is half a circle and we have to integrate $\int^{\pi}_{0} A(x)\, dx$
$=\int^{pi}_{0} \frac{\pi r^{2}}{2}\, dx=\int^{\pi}_{0} \frac{\pi (\frac{\sqrt{sin(x)}}{2)^{2}}{2}\,dx}= \frac{\pi}{4}$

>Essentially, you write the volume as an integral of the Area function A(x) wrt to dx and your job is the find the Area function for cross section at every x

Notice how finding an Area function is easy for a **Solid of Revolution**, i.e. a solid formed by revolving a curve about an axis of rotation.

![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-11-05-55-37]]

$V=\int^{b}_{a} A(x)\,dx=\int^{b}_{a} \pi R(x)^{2}\, dx= \pi \int^{b}_{a} R(x)^2\,dx$
This is thus a special case of the Washer Method (Volume by Slicing).

### Problem 
Find the volume of the solid obtained by revolving the region between $y= \frac{1}{\sqrt{x}}$ and the x-axis for $1 \leq x \leq 4$ about the x-axis

$$V=\pi \int^{4}_{1} (\frac{1}{\sqrt{x}})^{2} \,dx=\pi ln(4)$$
Note how the $R(x)$ function is not just $f(x)$ since the function can be rotated about any line. so $R(x)$ is the distance function between a curve and the axis of rotation, which if it happens to be the x-axis would be $f(x)$, else it wouldn't!

### Example 
Let R be the region between the curves $y=(x-4)^2$ and $y=16$. Find the volume of the solid obtained by revolving R about $y=16$.

![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-11-06-07-03]]
$V=\pi \int^{8}_{0} R(x)^{2}\, dx = \pi \int^{8}_{0} (16-(x-4)^{2)^{2}\, dx} = \pi \int^{4}_{-4} (16-u^{2})^{2}\, du \quad \{u=x-4\}$
$=2\pi \int^{4}_{0} (16-u^2)^2\,du$
$=2\pi(1024 - \frac{2048}{3} + \frac{1024}{5})$


Cross-Sections can also be donuts

![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-11-06-40-04|1000]]
$V=Vol_{outer}-Vol_{inner}=\pi \int^{b}_{a} (R(x)^{2}-r(x)^{2})\, dx$
>Washer Method Special Case — Donut Method

Remember, R(x) is not simply f(x)-a. (it kinda doesn't matter since it's being squared) but remember, it's a distance function... so it's |f(x)-a| which would hence give us the DISTANCE and hence the magnitude of the radius of rotation.

>You have to think here about whether something is making a donut and a function is an inner/outer radius of a donut or whether f(x)+g(x) is itself a radius... that is the curve is itself rotating around one of those functions 


---

# Where things get difficult:
```desmos-graph
left=-1; right=2;
bottom=-1; top=2;
---
y=x^6-x+1
y=1-x
x=1
```
let's take the area bounded by the curves here by the blue, green and purple curves.

That's easy. We can also find the volume of the solid of revolution around x-axis.

What if you spin around y-axis?

The problem is, it's hard to find everything in terms of the other variable

$y=x^6-x+1$ is hard to turn as a function of $x$ in $y$.


## Shell method
Another way to find volume.

Idea:
Divide R into slices that are parallel to the axis of revolution instead of perpendicular.


![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-16-05-54-27|1000]]
![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-16-05-59-08|1000]]

For the shell method, we break areas into little shells, the width of those shells being $\Delta x$

Volume of 1 cylindrical shell with an outer and inner radius R and r is:
$\pi R^{2}f(x)-\pi r^2f(x)$
$\pi f(x)(R^{2} -r^2)$
$\pi f(x)(R-r)(R+r)$
$\pi f(x)(R+r)\, \Delta x$  (since R-r is $\Delta x$)


Thus the total volume of the shells is
$$\sum^{n}_{i=1} \pi f(x)(R_i+r_i)\, \Delta x$$
where $\Delta x = interval/n$

Thus, the volume would be
$$V = \lim_{\Delta x \to 0}\sum^{n}_{i=1} \pi f(x)(R_i+r_i)\, \Delta x$$
for some interval [0, b]

$$\implies V = \pi \int^{b}_{0} f(x) \,2x$$
R and r both approach the same thing: $x$, the height is $f(x)$.


Thus in general,
$$V=2\pi \int_{a}^{b} (\text{Shell radius})\, (\text{shell height}) \,dx $$ (if revolving around vertical line)

Shell radius here is the distance from axis to where you slice.



```desmos-graph
left=-1; right=2;
bottom=-1; top=2;
---
y=x^6-x+1
y=1-x
x=1
```
![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-16-06-19-47]]
here consider a shell
![[Maths/Calc 2/Recitations/attachments/Drawing 24-09-16-06-21-04]]
The height of the shell at any point x would be $(x^6-x+1)-(1-x)=x^6=h$, the radius $R$ for outer and $r$ for inner.

The volume would be 
$Volume_{outer} - Volume_{inner}$
$= \pi R^2h-\pi r^2h$
$=\pi h (R^2-r^2)$
$=\pi h (R+r)(R-r)$
but for limiting value of R and r approaching x would mean it is the integral
$\int^{1}_{0} \pi h (2x) \,dx= \int^{1}_{0} \pi x^7 (2x) \,dx$
$=\pi/4$
easy!

![[Maths/Calc 2/Recitations/attachments/WhatsApp Image 2024-09-16 at 18.30.05_5aa9e78f.jpg]]

---
Another way to interpret this that I can think of is, you are integrating the volume $(2\pi r)*h$ over the entire interval

$$V = \int^{b}_{a} 2\pi x \cdot f(x) \,dx$$

![[Maths/Calc 2/Recitations/attachments/WhatsApp Image 2024-09-16 at 18.44.38_686e5d41.jpg]]

So remember:

## Washer method:
You integrate little washers/disks with slight thickness
Hence $(\pi R^{2} - \pi r^2)\,dx$

## Shell Method:
You integrate Curved surface areas of cylinders with slight thickness
Hence $(2\pi r h)\, dx = 2 \pi x f(x) \, dx$



---
![[Maths/Calc 2/attachments/Drawing 24-09-18-05-42-15|1000]]



Remember:
==Washer Method== is when you consider washers/donuts/simple circles and integrate. The $dx$ element is what direction you move linearly in and the Radius function $R(x)$ through which you calculate $A(x)$ can be a funky function. You integral little disks/donuts of width $dx$, hence volume $A(x)\,dx$

The Radius (and hence the Area) here can be a stupid function, the height is just the integrating element.

==Shell Method== is when you consider radially outward cylinders. Your radius moves out linearly and is the same is the integral nudge $dx$ in terms of direction. The height function can be funky. You basically take in cylinders at each of the radii and give them a thickness $dx$, hence the volume $2\pi r(x) \,h(x)\,dx, \quad r(x)$ being a linear function of $x$, usually $x$ itself unless your radius about some other axis, in which case it becomes $a+bx$. ^6319ed

Here you think about both the height and the radius. The Height can be a stupid function, the radius will have to be a linear function in the same variable as the integrating element.
