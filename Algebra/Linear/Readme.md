# Linear Equation

## What is a Linear Equation?

A linear equation is an algebraic equation of degree one, meaning the highest exponent of any variable in the equation is 1. When graphed, a linear equation always forms a straight line .

Purpose: It models relationships where the rate of change is constant. For every fixed increase in one quantity, the other quantity changes by a proportional, fixed amount.

### Where it is used?

1. Computer Graphics and Geometry
    
    Drawing lines and basic shapes, especially in 2D graphics engines.

    An algorithm called DDA (Digital Differential Analyzer) or Bresenham's Line Algorithm uses concepts derived from the slope-intercept form (y=mx+b) to determine which pixels should be lit up between two points to form a perfect straight line on a screen.

2. Memory Addressing

    Accessing data stored in a simple list or array in a computer's memory.

    The memory address of the n-th element in an array is calculated using a linear relationship:
    $$\text{Address} = \text{Base Address} + \text{n} \times \text{Size of one element}$$

## Operations

### 1. Basic Operations

* $2x$: **2 multiplied by $x$**
* $2/x$: **2 divided by $x$**
* $x/2$: **$x$ divided by 2**
* $x + 3$: **$x$ added to 3**
* $x - 3$: **$x$ subtracted by 3**

***

### 2. Equality of Terms 
$$\frac{1}{2}x == \frac{1x}{2} = \frac{1}{2x} == \frac{1x}{2x} ?$$

No above statement is not correct


#### Correct

$$\mathbf{\frac{1}{2}x = \frac{1x}{2}}$$
These two expressions are equal to $\frac{x}{2}$.

$$\mathbf{\frac{1x}{2x} = \frac{1}{2}}$$
These two expressions are equal to $\frac{1}{2}$.

***

### 3. Multiplication and Simplification

$$\mathbf{2x \cdot \frac{1}{x} = 2}$$

Your check with $x=4$ is perfect:
$$2x \cdot \frac{1}{x} = \frac{2(4)}{1} \cdot \frac{1}{(4)} = \frac{8}{4} = 2$$

***

### 4. Multiplication of Monomials

$$\mathbf{2x \cdot 1x = 2x^2}$$

check by substituting $x=4$:

$$2x \cdot 1x = 2(4) \cdot 1(4)$$
$$2x \cdot 1x = (8) \cdot (4)$$
$$2x \cdot 1x = \mathbf{32}$$

Now we check the resulting expression, $2x^2$:
$$2x^2 = 2(4)^2$$
$$2x^2 = 2(16)$$
$$2x^2 = \mathbf{32}$$

Since $32 = 32$, our calculation $\mathbf{2x \cdot 1x = 2x^2}$ is correct

### Simplify

1. $$\frac{3x}{3} + \frac{9}{3}$$

if a expression or term is like this we can written this as 

$$\frac{3(x+3)}{3}$$

We can cancel 3 from numerator and denominator
$$\frac{\cancel{3}(x+3)}{\cancel{3}} = (x+3)$$

so $$\frac{3x}{3} + \frac{9}{3} == \frac{3(x+3)}{3} == (x+3)$$

To verify subsritute x = 3, evey expression should return same result

$$\frac{3(3)}{3} + \frac{9}{3} == \frac{3(3+3)}{3} == (3+3)$$

$$\frac{3(3)}{3} + \frac{9}{3} \rightarrow equation 1$$
$$\frac{9}{3} + \frac{9}{3} \rightarrow \frac{18}{3} \rightarrow 6$$

$$\frac{3(3+3)}{3}  \rightarrow equation 2$$
$$\frac{9+9}{3} \rightarrow \frac{18}{3} \rightarrow 6$$

$$(3+3) \rightarrow equation 3$$
$$3+3 \rightarrow 6$$

hence it is verified

2. $$\frac{5(x+3)}{3}$$
Here we cannot cancel numerator and denominator 3

if we cancel repression will be $$\frac{5(x+\cancel{3})}{\cancel{3}} = 5x$$
Let's substitute x = 3
$$\frac{5(x+3)}{3} = \frac{5(3+3)}{3} = \frac{5(6)}{3} = \frac{30}{3} = 10 \rightarrow eq1$$
$$5x = 5(3) = 15 \rightarrow eq2$$

Hence it is not equal



### Exponents (Powers)


| Expression | Meaning | Example (if $x=3$) |
| :--- | :--- | :--- |
| $\mathbf{x^2}$ | $x$ multiplied by itself (x times x). | $3^2 = 3 \cdot 3 = 9$ |
| $\mathbf{x^3}$ | $x$ multiplied by itself three times. | $3^3 = 3 \cdot 3 \cdot 3 = 27$ |
| $\mathbf{x^n}$ | $x$ multiplied by itself $n$ times. | |

## Types of Linear equation

### 1. One Variable	


1. $$x−5.7=−1.2$$

Convert to integer: It is /10 decimal, so multiply by 10

$$10x (-5.7 \times 10) = -1.2 \times 10$$

$$10x-57=-12$$

Isolate x by removing -57 by addding +57
$$10x -57 + 57 = -12 + 57$$
$$10x = 45$$

Isolate x, by divide 10
$$\frac{10x}{10} = \frac{45}{10}$$
$$x=4.5$$

**Verify the solution**  

Substitute the x in place


$$4.5-5.7=-1.2$$
$$-1.2=-1.2 \text{ It is proved}$$

---

2. $$y+\frac{5}{8}=\frac{1}{4}$$

Find LCM of 8,4 = 8

$$\frac{y \times 8}{1 \times 8} + \frac{5 \times 1}{8 \times 1} = \frac{1 \times 2}{4 \times 2}$$

$$\frac{8y}{8} + \frac{5}{8} = \frac{2}{8}$$

Remove /8 by multiplying 8
$$\frac{8}{1}*\frac{8y}{8} + \frac{8}{1}*\frac{5}{8} = \frac{8}{1}* \frac{2}{8}$$

$$8y + 5 = 2$$

Combine constants

$$8y=2-5$$
$$8y=-3$$

Isolate y by divide 8

$$\frac{8y}{8}=\frac{-3}{8}$$
$$y=\frac{-3}{8}$$

**Verify**

$$\frac{-3}{8}+\frac{5}{8} = \frac{1}{4}$$
$$\frac{2}{8}=\frac{1}{4}$$
Simplify
$$\frac{1}{4}=\frac{1}{4}$$

### Solving Literal Equations
Solving Literal Equations: Equations where you solve for a specific variable in terms of other variables (e.g., solving A=P+Prt for r). This is essential preparation for working with formulas.

### Single-Variable Inequalities:
Equations that use <,>,≤,≥. The solving process is the same, with the added rule that you must reverse the inequality sign if you multiply or divide by a negative number.



### 2. Two Variables 
### 3. n variables..


### 4. Equation with Variables on Both Sides