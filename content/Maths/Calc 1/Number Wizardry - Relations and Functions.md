I would like to start the journey by discussing the major tools we're going to have that allows us to relate and play around with numbers and ideas.

$$\textbf{Relations and Functions}$$

---
You can think of them as Magic Boxes.

Put things inside, and it'll spit things out.

![[Maths/Calc 1/attachments/Drawing Magic Box]]

All right so... let's make it cook!


But first! Let's see what we have.
1. The Ingredients
2. The Cookbook

The Ingredients are the things we have before cooking. 
In Mathematics, it's called a **Domain**. You can have eggs, bread, *Numbers*, anything.

You can then turn those into some meal from the Cookbook, or the **Co-Domain**. And by meal, I mean ANYTHING.

So we process things from the Domain into things inside the Co-Domain. We clear? Cool!

## Relations

A Relation is a mad wizard.
It can turn anything up its head (as long as it wishes to do that).

You can give it things from the Ingredients, and it'll make you things in the cookbook, depending on what it wishes to make.

So it can **Relate** the cooked items to the ingredients.

Let's take a look at a what a few of the wizards cook...


![[Maths/Calc 1/attachments/Drawing Human Set to Num]]

I was not kidding. It can literally turn anything into anything else. So it can turn the detective into numbers 1, 2, and 3 (more fun that turning into a toad). It can take the cowboy and turn it into 3 and 5. As for the lady, she turns into a nice 8!

A bit more mathematically, 
the detective **relates** to the numbers 1, 2 and 3; the cowboy **relates** to 3 and 5 & the lady **relates** to the number 8.

Here, The detective, the cowboy, and the lady are $elements$^[Elements: members] of the $\text{Human Set}$^[Set: a collection of items]. This is our $Domain$.

The numbers are part of the $\text{Number Set}$. There's several of those… we can play with a simple one, $\text{Natural Numbers}$^[Natural Numbers: The Number Set $\{1,2,3,4\dots\}$. All Positive Integers.]. Natural Numbers are denoted by the symbol $\mathbb{N}$ (just a cool looking N for Natural). $\mathbb{N}$ is our $Co-Domain$.

The wizard $\text{Willow}\colon \text{Human Set} \rightarrow \mathbb{N}$, i.e. it's a relation defined on elements from the Human Set (the Domain) to those in the Natural Numbers (the Co-Domain).
Willow relates the following *ordered* pairs:

$$\begin{array}{rl}
(\text{detective}, & 1)\\
(\text{detective}, & 2)\\
(\text{detective}, & 3)\\
(\text{cowboy}, & 3)\\
(\text{cowboy}, & 5)\\
(\text{lady}, & 8)
\end{array}$$
Thus we can define the Relation $W$ (for willow)

$$W = \set{
(\text{d}, 1),
(\text{d}, 2),
(\text{d}, 3),
(\text{c}, 3),
(\text{c}, 5),
(\text{l}, 8)
}$$
$d=detective$
$c=cowboy$
$l=lady$

Willow's weird!

---

The next wizard, Merlin hates the pathetic Human Set. It likes the sweet world of Natural Numbers.

![[Maths/Calc 1/attachments/Drawing Number Set]]
Merlin, as it seems, also has a nice pattern to himself!
$$M\colon\mathbb{N}\rightarrow\mathbb{N},\quad M= \begin{align*} &\{(1,1), (2,2), (2,3), (3,4), (3,5),\\ &(3,6), (4,7), (4,8), (4,9), (4,10)\} \end{align*}$$
Hopefully, You can make sense of what that means.

$M=\{...\}$ means $M$ is a set. 
$M\colon\mathbb{N}\rightarrow\mathbb{N}$ indicates that the set is specifically a relation from the Natural Numbers to the Natural Numbers (so it's defined entirely in $\mathbb{N}$)
$(1,2), (2,2)...$ are the relations that Merlin defines.

---

So you get the Idea… You can define 2 things/numbers to relate through a relation. 

You can also define one more rigorously like
$$R = \{(x,y): x+y=2k, \quad x,y,k \in \mathbb{N}\}$$
This can be read out as a relation R that relates 2 Natural Numbers ($x$ and $y$) such that their sum is also an even Natural Number.

So $x$ and $y$ here can be $1$ and $3$ or 1 and $1729$ or $2$ and $2$.
The set/container of such a relation has an infinite number of elements.
$R=\{(1,1), (1,3), (2,2), (1,1729)\dots\}$ is an infinite set.

---

You can define all ingredients to be related to all the items in the cookbook. 
That is called a Cartesian Product.

![[Maths/Calc 1/attachments/Drawing Cartesian Product]]
This is also a relation where all elements in set $A$ (the numbers) relate to elements in the set $B$ (the shapes).

So The above relation can be the Cartesian Product $\mathbb{N}\times Shapes$.

($\mathbb{N}\times\mathbb{N}$ for instance would be the set $\{(1,1),(1,2),(1,3)\dots,(2,1), (2,2)\dots, (3,1), (3,2)\dots\}$)


So a Relation is really anything you define it to be. You can have two numbers relate to each other. Or not relate to each other. Depends on the conditions of the relation.

---

Certain sophisticated wizards however are more famous for their cooking than others.

A relation, although useful can be pretty broad and messy.
A more specialized relation is called a function.

# Function

A function, is a relation in which only 1 ingredient (an element in the Domain) relates to only 1 meal in the cookbook (an element in the Domain)

![[Maths/Calc 1/attachments/Drawing func depiction]]

---

A function is a very simple relation.
**It takes in a single *input* and spits out a single *output*.** That's it. ^a5fa57

It is very predictable, in a sense that an input can only be assigned a single output value. And this style of cooking is particularly useful!

---
Let's take a look at a more spacial visualization of numbers than Sets shall we? Behold… 

## The Realm of Plots 

A **Real-Valued Function**, usually denoted in maths by $f(x)$, $y$ or $y(x)$ simply takes in a number, and outputs a real number (unless undefined). 

![[Maths/Calc 1/attachments/Drawing Func vs Rel Plots]]

Figure 1 is both a function and a relation.
Figure 2 is only a relation. It is NOT a function. 

Functions do NOT spit out multiple values for the same input. Only many-one relations/multivalued relations do that.

A quick "Vertical Line Test" as depicted in the image can be done to see if a curve is a function or not.

---

# Scrooting a number

I would like to touch on a very special function here. 
The Square Root Function.

Once you get the gist of understanding this one, you're good to go.

So, here's a question:

$$x^2=4$$
$$x=\sqrt{4} \enspace or \enspace x=\pm\sqrt{4}$$
$$x=\pm2$$
which one of these is correct? Should there be a $\pm$ symbol in front of the square root or not?

Personally, I felt the $\pm$ symbol is redundant.

Usually, we like to think that the Square-Root is an *inverse* of the Square function. In a sense that it tends to _undo_ what the other does.

For instance, $\sqrt{(a^2)}= a$.

And while that is the purpose, there's a catch.

![[Maths/Calc 1/attachments/Drawing Sqrt Function|1000]]

Let's take a look at $fig. 1$ first. 

In violet, you see the function $\color{#6741d9} y=x^2 \enspace \{f(x)\}$ plotted. It just squares each input.
(Notice how 2 ingredients can validly cook into the same meal but not the other way around)


>A nice #funfact when dealing with graphs, is that reflecting a function $f(x) = y$ about $\color{#ff8787} y=x$ would give you a sort of inverse **relation** $f(y)=x$.

So in $fig. 1$, the grey reflection $\color{grey}x=y^2$ is the inverse relation of our function $\color{#6741d9}y=x^2$.
(in case you missed it, the $x$ and $y$ positions got swapped)

* <span style="color: #6741d9;">Maps out Meals for each Ingredient</span>
* <span style="color: #868e96;">Maps back each of the ingredients for the meals</span>

For instance, you invert points
$\color{#6741d9}(-3, 9)$ & $\color{#6741d9}(3, 9)$ $\rightarrow$ $\color{grey}(9, -3)$ & $\color{grey}(9, 3)$
$\color{#6741d9}(ingredient, meal)$ $\rightarrow$ $\color{grey}(meal, ingredient)$


Now, let's look at the actual Square Root Function in $fig. 2$. 

Notice, now that the plot for $\color{#6741d9}y=\sqrt{x}$ is not entirely the same as the inverse relation in $fig. 1$!
It misses the bottom bit that would have otherwise been there if it were a true inversion. 

And that is on purpose. Notice how otherwise, the entire thing would have failed the vertical line test! In other words, there would've been two outputs for the same input!

But by the [[Maths/Calc 1/Number Wizardry - Relations and Functions#^a5fa57|definition of a function]] as defined at the top of this page, It wouldn't be a function.

> A function takes in a single input, and spits out a single output!

Hence, to call the Square Root a function, we had to make a choice. Which branch of the inversion to assign to the Square-Root function? The top one? Or the bottom one?

In simpler terms, to avoid having a single input like $16$ output 2 distinct values as $\sqrt{16} = -4, 4$ which would then, by definition invalidate "Square-Root" as a function, we had to pick a side.
$$\sqrt{16} = -4 \quad \text{or} \quad \sqrt{16}=4$$

Because the purpose of the function emerged from physical geometry, we went for the top (***positive***) output branch.

This ensured that the length of **hypotenuses** remained positive. They had to! They were distances.
(an obvious use case of the square-root function: $C = \sqrt{A^{2}+ B^2}$. Yes, these functions were thought of way back by the ancient Greeks!)

That means, $\sqrt{16}=4$**.** **Period.**

So there you have it!

# Conclusion

The $\sqrt{\hphantom{x}}$ symbol you often see in maths, like a lot of other things, is a function! 

And because functions are defined to just be a processing unit that would, 
>“take in a single input and spit out a single output”

functions like these often have to have assigned to a certain branch of the Co-domain, to maintain a one-to-one correspondence that a function has.

A Square-Root function, is thus defined to output a single non-negative real value for a single non-negative input value.

So $\sqrt{25} = 5$ even though both $5^2=(-5)^2=25$.

So to answer the question, $$x^{2}=4\implies x = \pm \sqrt{4}$$
since the $\sqrt{4}$ part only had to be the positive value $+2$.


>(Ignore the following if you're unfamiliar with Complex Numbers)

A #cheesy thing about this is that the Square-Root function is NOT defined to output only Positive Numbers. ^1073f2

Remember, it was only necessary to pick a certain branch because we had to avoid redundancies of multiple outputs for a single input.

So we can validly extend the Square-Root function into the complex world.

We CAN say $$i=\sqrt{-1}$$
we did however, had to pick a ”Positive imaginary number branch” here too since $(-i)^2$ also equates to $-1$.

# The Final Verdict for The End of the Beginning

There are other functions… all kinds of functions! Polynomials, Exponents, Factorials, Trigonometric functions, what not!

All processing and cooking the input in some weird way or the other. Some have restrictions over Domains, some chose a certain Branch from within the Co-Domain.

Few flow smoothly, few have bends and holes and what not!

Wizards! Ahhh!

The idea of a function, beyond maths entails an even broader story where it pretty much behaves like a Relation, i.e. it can take in arbitrary number of inputs and output arbitrary many outputs!

But as of now, we'll broadly deal with Functions that give us enough power to cook stuff out of numbers.

Know more about the behavior of functions... [[Maths/Calc 1/Limits|Limits]]




















