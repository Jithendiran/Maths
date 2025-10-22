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

#### Solving Literal Equations
Solving a literal equation means rearranging the equation to isolate a specific variable in terms of the others. You use the exact same algebraic operations (addition, subtraction, multiplication, division) as you would for numerical equations, but you apply them to variables instead of numbers.

##### Example

**1. Solve the formula for the area of a rectangle, $A = lw$, for the variable $w$ (width)**

$$\text{A= lw}$$
1. The variable $l$ is currently multiplying $w$.
2. To isolate w, divide both sides by l:
$$\frac{A}{l} = \frac{l w}{l}$$
3. Simplify:$$\mathbf{w = \frac{A}{l}}$$

**2. Solve the simple interest formula, $I = Prt$, for the variable $t$ (time).**
$$\mathbf{I = P r t}$$

1. The variables $P$ and $r$ are currently multiplying $t$.
2. To isolate t, divide both sides by the product Pr:
$$\frac{I}{P r} = \frac{P r t}{P r}$$
3. Simplify:$$\mathbf{t = \frac{I}{P r}}$$

**3. Solve the formula for the perimeter of a rectangle, $P = 2l + 2w$, for the variable $l$ (length).**
$$\mathbf{P = 2 l + 2 w}$$
1. Isolate the term containing l by subtracting 2w from both sides:$$P - 2w = 2l$$

2. To isolate l, divide the entire expression on the left side by 2:$$\frac{P - 2w}{2} = \frac{2l}{2}$$

3. Simplify:$$\mathbf{l = \frac{P - 2w}{2}}$$

#### Single-Variable Inequalities:
A linear inequality uses an inequality symbol instead of an equals sign. It represents a range of values that satisfy the condition, not just a single value.

| Symbol | Meaning | Example |
| :--- | :--- | :--- |
| **$<$** | less than | $x < 5$ |
| **$>$** | greater than | $x > 5$ |
| **$\le$** | less than or equal to | $x \le 5$ |
| **$\ge$** | greater than or equal to | $x \ge 5$ |

##### Solving Single-Variable Inequalities
The process for solving single-variable linear inequalities is very similar to solving single-variable equations, with one crucial difference:

1. **Isolate the variable**: Use the same inverse operations (addition, subtraction, multiplication, division) on both sides of the inequality to isolate the variable, just as you would for an equation.

2. **The Multiplication/Division Rule**: If you multiply or divide both sides of the inequality by a **negative number**, you must reverse the direction of the inequality symbol.

$$2 < 5$$
Now, multiply both sides by $-1$:
$$-2 < -5 \quad (\text{FALSE})$$
To keep the statement true, you must invert the sign:$$-2 > -5 \quad (\text{TRUE})$$

**Examples**

$$10 - 2x < 4$$
Eliminate 10 by -10 on both side
$$\cancel{10} - 2x  \cancel{-10}< 4 - 10$$
$$-2x<-6$$
Divide both sides by −2 and reverse the inequality symbol:$$\frac{-2x}{-2} > \frac{-6}{-2}$$
$$x > 3$$
The solution is all numbers greater than 3.

**A cell phone company offers a plan for $30 per month plus a fee of $0.05 per text message. If a customer wants their total monthly bill to be no more than $45, what is the maximum number of text messages ($t$) they can send?**

Fixed Cost: $30.00

Variable Cost: $0.05 per text message ($t$)

Total Cost: $30 + 0.05t$

Constraint: The total bill must be "no more than \$45," which means less than or equal to ($\le$) $45.
$$\text{Total Cost} \le \text{Maximum Budget}$$

$$30 + 0.05t \le 45$$

Subtract 30 from both sides:$$0.05t \le 45 - 30$$
$$0.05t \le 15$$

Divide by the positive number 0.05. (Since we are dividing by a positive number, the inequality sign does not flip.)
$$t \le \frac{15}{0.05}$$

$$t \le 300$$

##### Compound Inequalities
A compound inequality combines two simple inequalities using the words "and" or "or."

* "And" (Intersection): The solution must satisfy both inequalities. These are often written in a compact form:$$-5 \le 3x + 1 < 10$$
(Means $-5 \le 3x + 1$ AND $3x + 1 < 10$). Solve all three parts simultaneously.
* "Or" (Union): The solution must satisfy at least one of the two inequalities. Solve each inequality separately:$$x + 1 < 3 \quad \text{or} \quad 4x - 5 > 15$$

Example: 
* $$−7\le2x−1<5$$
1. Add 1 to all three parts:
$$−7+1\le2x−1+1<5+1$$
$$−6\le2x<6$$
2. Divide by 2 (a positive number) in all three parts:
$$-3 \le x < 3$$
"Solution: $−3 \le x<3$ or in interval notation, [−3,3)."

* $$3x+1 \le −5 OR 4x−5>7$$
Solve $3x + 1 \le -5$

(Subtract 1) $$3x \le -6$$
(Divide by 3) $$x \le -2$$

Solve $4x−5>7$

(Add 5) $$4x > 12$$
(Divide by 4) $$x > 3$$

Solution: $x \le -2 \text{ OR } x > 3$.

Interval Notation: $(-\infty, -2] \cup (3, \infty)$ (The $\cup$ symbol represents the union of the two sets.)

#### Refer
1. [More](./linear-single.md)
2. [cleaning](./linear-awkward.md)
3. [Combination](./linear-single.md#important)

#### Todo
1. Absolute Value Equation


### 2. Two Variables 

A linear equation in two variables, typically $x$ and $y$, is one that can be written in the form:$$\mathbf{Ax + By = C}$$

where $A$, $B$, and $C$ are real numbers, and $A$ and $B$ are not both zero.

solution is a pair of numbers $(\mathbf{x, y})$ that makes the equation true. Stress that there are **infinitely many solutions**.

**infinitely many solutions. means does signle variable has only one solution?**

*Single variable*
----

A standard linear equation with one variable, like $x$, represents a single, specific point on a number line.
$$2x + 5 = 11$$
Solution: Subtract : $2x = 6$ Divide by 2: $x = 3$.

The only number that makes this statement true is $3$. You are looking for a single, fixed location on a 1-dimensional number line.

Some exceptions for single variable is 
* Zero (No Solution) 
$$2x + 4 = 2x + 7$$
Subtract $2x$: $4 = 7$ This is false, so no value of $x$ can solve it.

* Infinitely Many Solutions
$$3x + 6 = 3(x + 2)$$
Simplify RHS: $3x+6=3(x+2)$ This is always true, so any value of x works.

*Two variable*
----

A standard linear equation with two variables, like $x$ and $y$, represents a relationship between two quantities

$$y = 2x + 1$$

Solutions: A solution is an ordered pair $(x, y)$
* If $x=1$, $y=3$ Solution: $(1, 3)$
* If $x=0$, $y=1$ Solution: $(0, 1)$
* If $x=-5$, $y=-9$ Solution: $(-5, -9)$

----

#### solve

$$5x + y = 10$$

Let's solve x

x is multiplied with 5 so

$$x + \frac{y}{5} = 10$$

isolate the x

$$x = 10 - \frac{y}{5}$$

Looks like to know x, we 1st have to find y

$$5x + y = 10$$

Let's solve y

isolate the y

$$y = 10-5x$$

To find y we first solve x, What!!! again

May be there is a way like this

$$x = 10 - \frac{y}{5}$$
$$y = 10-5x$$

substitute y in x

$$x = 10 - \frac{(10-5x)}{5}$$
$$x = 10 - \frac{\cancel{5}(2-x)}{\cancel{5}} = 10-(2-x) = 10-2+x$$
$$x = 8 + x$$
Isolate x by adding -x
$$x-x = 8$$
$$0 = 8$$

The fact that the variables canceled out and you ended up with the false statement ($\mathbf{0 = 8}$)

Let's pick x = 4

substiture x = 4 in equation

$5x + y = 10$

$$5(4) + y = 10$$
$$20 + y = 10$$
$$y = 10 - 20 = -10$$

This may the right method, now we have both x and y, substitute in main equation
$$x=4, y =-10$$
$$5(4) + (-10) = 10$$
$$20-10 = 10$$
$$10=10$$

$10=10$ is always true, it means that the equations you combined were dependent on each other (they were different forms of the same rule).

This is a valid solution! It's just one of the infinitely many points on the line $5x + y = 10$.
$$(x,y)=(4,-10)$$
if x = 4 solution is -10, if x is different, y will be different


**The Takeaway**
* The goal in these problems is not to find one single number for $x$ and $y$.
* The goal is to find the rule ($y = 10 - 5x$) and a set of points (like $(2, 0)$, $(0, 10)$, and $(4, -10)$) that satisfy that rule.
* The only time you would find a single, unique $(x, y)$ solution is if you were solving a system of two different linear equations (two intersecting lines), which is the next major topic after graphing!

#### Solv

$$5x + y = 10$$

1. $x = 0$
$$5(0) + y = 10$$
$$y=10$$
When x = 0, y is 10

**Verify**

$$5(0)+10 = 10$$
$$10 = 10$$

2. $x=1$
$$5(1)+y=10$$
$$5+y=10$$
subtract by 5 both side
$$y=5$$

**verify**
$$5(1) + 5 = 10$$
$$10=10$$

>[!NOTE] 
>what should we do now?  
>The value of one variable depends on the value of the other. You can't find a single numerical value for $x$ or $y$ until you choose a value for the other variable. How to choose number wisely?  
?Find three or more ordered pairs that satisfy the equation. The "wise choice" is simply to pick easy numbers like $x=0$, $x=1$, and $x=-1$, because they make the arithmetic simple.


#### Systems of Equations

A System of Equations is simply a collection of two or more equations that you consider at the same time.

Imagine you are looking for a secret number combination $(x, y)$

1. If you only have Rule 1
* Rule 1: "The first number ($x$), when multiplied by 5 and added to the second number ($y$), must equal 10." ($5x + y = 10$)
* Result: Many pairs work: $(2, 0)$, $(1, 5)$, $(0, 10)$, etc. You can't be sure which one is the secret combination.

2. If you add Rule 2 (A System):
* Rule 2: "The second number ($y$) must also be 2 less than the first number ($x$)." ($y = x - 2$)
* Result: You are looking for the one pair that satisfies both rules simultaneously. This is the point of agreement between the two rules.

By forcing the solution to obey two different rules, you reduce the infinite possibilities down to usually just one unique pair: $\mathbf{(2, 0)}$.

#### Methods for Solving Systems of Linear Equations

1. **Substitution**,"Solve one equation for one variable (e.g., y in terms of x), then substitute that expression into the other equation. This reduces the system to a single linear equation in one variable, which you can then solve."
2. **Elimination** (or Addition),"Multiply one or both equations by a number so that when the equations are added together, one of the variables is eliminated. This leaves a single equation in the remaining variable."
3. **Graphing**,Graph both lines on the same coordinate plane. The point where the two lines cross is the solution. This is often the least accurate method unless done with a graphing calculator.

#### Types of solutions in Systems of Linear Equations

1. **One Solution**: The lines cross at a single point (the standard case).
2. **No Solution**: The lines are parallel (same slope, different $y$-intercepts).
3. **Infinitely Many Solutions**: The two equations describe the exact same line (dependent equations).

[Practice](./linear-double.md)

#### Inequalities

The solution to a linear inequality like $Ax + By < C$ is not a single ordered pair $(x, y)$, but an infinite set of ordered pairs that make the inequality true.

eg:
$$2x - y \le 5$$

**Question 1: Is the point $(4, 1)$ a solution?**
1. Substitute $x=4$ and $y=1$ into the inequality:$$2(\mathbf{4}) - (\mathbf{1}) \le 5$$

2. Simplify:$$8 - 1 \le 5$$
$$7 \le 5$$

Conclusion: This statement is False. Therefore, $(4, 1)$ is NOT a solution.

**Question 2: Is the point $(1, -2)$ a solution?**

Substitute $x=1$ and $y=-2$ into the inequality:$$2(\mathbf{1}) - (\mathbf{-2}) \le 5$$

Simplify:$$2 + 2 \le 5$$

$$4 \le 5$$

Conclusion: This statement is True. Therefore, $(1, -2)$ IS a solution.

### TODO
* Graph the Boundary Line
* Shade the Solution Region

##### System of Linear Inequalities


#### Graph plots

1. coordinate Plane
2. Cartesian plane
3. Intercepts
4. The Slope ($m$)
5. Slope-Intercept Form

### 3. n variables..
