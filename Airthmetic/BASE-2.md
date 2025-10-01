## Addition

### Rules
$$
0 + 0 = 0 \\  
0 + 1 = 1 \\  
1 + 0 = 1 \\  
1 + 1 = 10  (which\ is\ 0\ with\ a\ carry\ of\ 1\ to\ the\ next\ bit) \\  
$$

### Example

1. 
 0 + 1 = 1
    Answer in decimal is 1, with 0 carry

2.   
```
1 + 1 = 10
place value
            4   2   1
carry:          1
                -------    
                    1 
                    1
                --------
                 1  0

    Decimal
    1 + 1 = 2, 2 => 10

```   

In binary we have only two symbols which is 0 and 1, when the place value reaches 1, for nect digit we will form a group of 2, 1 + 1 = 10 whcih mean 1 group of 2's and 0 extras

3. 

```
 1 + 1 + 1 = 11
place value
            4   2   1
carry:          1
                -------    
                    1 
                    1
                --------
                 1  0
                    1
                --------
                 1  1

    Decimal
    1 + 1 + 1 = 3, 3 => 11

```

11 means 1 group of two's and 1 extra unit

4. 

```

1101+1011 =  11000

palce value
            128 64  32  16  8   4   2   1 
        ----------------------------------
carry
                        1   1   1   1
        ----------------------------------
                            1   1   0   1
                            1   0   1   1
        ----------------------------------
                        1   1   0   0   0

```
1 group of 16, 1 group of 8, 0 group of 4, 0 group of 2 and 0 extra, so the result is 16 + 8 = 24

### How computers do?

To perform addition computer needs two input (A nand B) and two output (sum and carry)

#### Half added

Used for adding two single bits (no carry-in). It has two inputs (A and B) and two outputs: the sum and the carry.

- **Sum** = A XOR B (exclusive OR: 1 if exactly one input is 1).
- **Carry** = A AND B (AND: 1 inly if both inputs are 1)

| A | B | Sum (A XOR B) | Carry (A AND B) |
|---|---|----------------|-----------------|
| 0 | 0 | 0              | 0               |
| 0 | 1 | 1              | 0               |
| 1 | 0 | 1              | 0               |
| 1 | 1 | 0              | 1               |

#### Full Adder

Extends the half adder to handle a carry-in from a previous addition, making it suitable for multi-bit addition. It has three inputs (A, B, and Carry-in) and two outputs (Sum and Carry-out).

- **Sum** = A XOR B XOR Carry-in.
- **Carry-out** = (A AND B) OR (B AND Carry-in) OR (A AND Carry-in).

| A | B | Carry-in  | Sum | Carry-out  |
|---|---|-----------|-----|------------|
| 0 | 0 |    0      |  0  |     0      |
| 0 | 0 |    1      |  1  |     0      |
| 0 | 1 |    0      |  1  |     0      |
| 0 | 1 |    1      |  0  |     1      |
| 1 | 0 |    0      |  1  |     0      |
| 1 | 0 |    1      |  0  |     1      |
| 1 | 1 |    0      |  0  |     1      |
| 1 | 1 |    1      |  1  |     1      |

Example with Full Adder
-----------------------

     101    
    +110  

**Bit 0:** Inputs A=1, B=0, Carry-in=0. Sum = 1 XOR 0 XOR 0 = `1`, Carry-out = (1 AND 0) OR (0 AND 0) OR (1 AND 0) = `0`.  

**Bit 1:** Inputs A=0, B=1, Carry-in=0. Sum = 0 XOR 1 XOR 0 = `1`, Carry-out = (0 AND 1) OR (1 AND 0) OR (0 AND 0) = `0`.

**Bit 2:** Inputs A=1, B=1, Carry-in=0. Sum = 1 XOR 1 XOR 0 = `0`, Carry-out = (1 AND 1) OR (1 AND 0) OR (1 AND 0) = `1`.

**Bit 3:** Carry-out = `1` becomes the most significant bit.

Result: `1011`, computed bit by bit using adders.

#### Handling Larger Numbers

Computers represent numbers using fixed-size registers (e.g., 8-bit, 16-bit, 32-bit, or 64-bit). For a 32-bit addition, 32 full adders (or a combination starting with a half adder) work in parallel or sequentially, depending on the architecture. If the sum exceeds the register size, an overflow occurs, which may trigger a flag or require special handling in software.

**Carry-Lookahead Adder (CLA)**
--------------------------------------

**What**: Instead of waiting for carries to propagate bit by bit (ripple-carry adder), a CLA computes carries for multiple bits simultaneously.

**Why it works**: It uses additional logic to predict carry-out for each bit based on "generate" (A AND B) and "propagate" (A OR B) conditions, reducing delay.

**How**:
* Generate: G = A AND B (carry is generated if both inputs are 1).
* Propagate: P = A OR B (carry passes through if at least one input is 1).
* Carry-out for bit i: C_i+1 = G_i OR (P_i AND C_i).
This allows parallel computation of carries, speeding up addition for large numbers.

**Example**

* **Step 1: Compute Generate and Propagate Signals**
- `G = A AND B `, `P = A OR B`

- Bit 0: A_0=1, B_0=1

    G_0 = A_0 AND B_0 = 1 AND 1 = 1
    P_0 = A_0 OR B_0 = 1 OR 1 = 1

- Bit 1: A_1=1, B_1=0

    G_1 = A_1 AND B_1 = 1 AND 0 = 0
    P_1 = A_1 OR B_1 = 1 OR 0 = 1

- Bit 2: A_2=0, B_2=1

    G_2 = A_2 AND B_2 = 0 AND 1 = 0
    P_2 = A_2 OR B_2 = 0 OR 1 = 1

- Bit 3: A_3=1, B_3=1

    G_3 = A_3 AND B_3 = 1 AND 1 = 1
    P_3 = A_3 OR B_3 = 1 OR 1 = 1

* **Step 2: Compute Carry Bits**
- Initial carry is `0`, formula for other bits `C_i+1 = G_i OR (P_i AND C_i)`

- C_0 = 0

- C_1 (carry into bit 1):

    C_1 = G_0 OR (P_0 AND C_0) = 1 OR (1 AND 0) = 1 OR 0 = 1

- C_2 (carry into bit 2):

    C_2 = G_1 OR (P_1 AND C_1) = 0 OR (1 AND 1) = 0 OR 1 = 1

- C_3 (carry into bit 3):

    C_3 = G_2 OR (P_2 AND C_2) = 0 OR (1 AND 1) = 0 OR 1 = 1

- C_4 (carry-out from bit 3, the final carry):

    C_4 = G_3 OR (P_3 AND C_3) = 1 OR (1 AND 1) = 1 OR 1 = 1

* **Step 3: Compute Sum Bits**
For each bit, `S_i = A_i XOR B_i XOR C_i`:
- Bit 0: S_0 = A_0 XOR B_0 XOR C_0 = 1 XOR 1 XOR 0 = 0
- Bit 1: S_1 = A_1 XOR B_1 XOR C_1 = 1 XOR 0 XOR 1 = 0
- Bit 2: S_2 = A_2 XOR B_2 XOR C_2 = 0 XOR 1 XOR 1 = 0
- Bit 3: S_3 = A_3 XOR B_3 XOR C_3 = 1 XOR 1 XOR 1 = 1

* **Step 4: Assemble the Result**
- Sum bits: S_3 S_2 S_1 S_0 = `1000`
- Carry-out: C_4 = `1`
- Final result: C_4 S_3 S_2 S_1 S_0 = `11000`

#### Addition with negative number

#### How sign rule will work

## Subtraction

### Rule  

$$
1 - 1 = 0 \\
1 - 0 = 1 \\
0 - 1 = -1 \\
0 - 0 = 0 \\
10 - 1 = 1 (borrow)\  from\ next\ higher\ value\ exchange\ for\ 2\ groups
$$

### Example 

1. 1 1 0 - 1 0 1

```

    1   1   0
    1   0   1
    ---------
```

- 0 - 1, 0 is smaller to do subtraction, so we have to exchange 2 value from next higher digit

```
    1   0   10
    1   0   1
    ---------
    0   0   1
```

2.  1   1    0   0   1 - 0   1    1   1   1

Step 1: The Ones Column
`1 - 1 = 0`. This is still the same.

```
    1       1       0       0      1
-   0       1       1       1      1
    ----------------------------------
                                    0
```

Step 2: The Borrow Chain 

* Twos Column: We need to do 0 - 1. We must borrow.  
* Fours Column: It's a 0. Can't help.  
* Eights Column: We take the 1 from here. It becomes 0. This 1 (which is worth eight) moves to the Fours column and becomes "two" Fours, which we write as 10.

```
    1       0       10      0      1
-   0       1       1       1      1
    ---------------------------------
                                    0

```

* Now we borrow from the Fours column to help the Twos column. The Fours column has a value of "two" (written as 10). We take "one" from it, leaving "one". So, the 10 is crossed out and becomes 1.
(In fourth place value we have 2 which is equalent of 8, so borrow 1 four to the second place value, which will become 10 in two's place value meaning two 2's (which is worth of 4))

* Now eighth place value is 0 which is not sufficient so borrow 2 from the 16th place value 
```

    0       10      1      10      1
-   0       1       1       1      1
    --------------------------------
    0       1       0       1       0

```
as a result we get  01010

### How computers do?

Computers take 2's complement and do addition, see [subtract](../Number_system/BASE-2.md)

Also there was a seperate circut for subtract : **full subtractor**, but they don't use now a days

* **Difference ($D$)**: The difference output is 1 if an odd number of inputs are 1. This is the exact definition of an **XOR** (Exclusive OR) operation.
    * $D = A\ XOR\ B\ XOR\ B_{in}$

* **Borrow-out ($B_{out}$)**: A borrow is needed if you are subtracting a 1 from a 0, or if you have a borrow-in and are subtracting from a 0.
    * $B_{out} = \bar{A}\ and\ B + \bar{A}\ and\ B_{in} + B\ and\ B_{in}$

### Example

A = 101, B = 011
5 - 3 = 2

## Full Subtractor Example

Let's subtract a 3-bit number $B = 011$ from another 3-bit number $A = 101$ using a chain of three full subtractors. 

**The problem in decimal is $5 - 3 = 2$.**

We will process the subtraction bit by bit, from right to left (Least Significant Bit to Most Significant Bit), with each full subtractor handling one column.

#### Bit 0 (Rightmost Bit)
* **Inputs:**
    * Minuend Bit ($A_0$) = 1
    * Subtrahend Bit ($B_0$) = 1
    * Borrow-in ($B_{in}$) = 0 (since this is the first bit, there's no borrow from a previous step)
* **Logic:**
    * **Difference ($D_0$)**: $D_0 = A_0\ XOR\ B_0\ XOR\ B_{in} = 1\ XOR\ 1\ XOR\ 0 = 0$
    * **Borrow-out ($B_{out}$)**: $B_{out} = \bar{A_0}\ *\ B_0 + \bar{A_0}\ *\ B_{in} + B_0\ *\ B_{in} = \bar{1}\ *\ (1) + \bar{1}\ *\ (0) + 1\ *\ (0) = 0\ *\ (1) + 0\ *\ (0) + 1\ *\ (0) = 0 + 0 + 0 = 0$
* **Result for Bit 0:**
    * Difference bit = 0
    * Borrow-out = 0 (this becomes the borrow-in for the next bit)

#### Bit 1 (Middle Bit)
* **Inputs:**
    * Minuend Bit ($A_1$) = 0
    * Subtrahend Bit ($B_1$) = 1
    * Borrow-in ($B_{in}$) = 0 (from the previous step's borrow-out)
* **Logic:**
    * **Difference ($D_1$)**: $D_1 = A_1\ XOR\ B_1\ XOR\ B_{in} = 0\ XOR\ 1\ XOR\ 0 = 1$
    * **Borrow-out ($B_{out}$)**: $B_{out} = \bar{A_1\ *\ }B_1 + \bar{A_1}\ *\ B_{in} + B_1\ *\ B_{in} = \bar{0}\ *\ (1) + \bar{0}\ *\ (0) + 1\ *\ (0) = 1\ *\ (1) + 1\ *\ (0) + 1\ *\ (0) = 1 + 0 + 0 = 1$
* **Result for Bit 1:**
    * Difference bit = 1
    * Borrow-out = 1 (this becomes the borrow-in for the next bit)

#### Bit 2 (Leftmost Bit)
* **Inputs:**
    * Minuend Bit ($A_2$) = 1
    * Subtrahend Bit ($B_2$) = 0
    * Borrow-in ($B_{in}$) = 1 (from the previous step's borrow-out)
* **Logic:**
    * **Difference ($D_2$)**: $D_2 = A_2\ XOR\ B_2\ XOR\ B_{in} = 1\ XOR\ 0\ XOR\ 1 = 0$
    * **Borrow-out ($B_{out}$)**: $B_{out} = \bar{A_2}\ *\ B_2 + \bar{A_2}\ *\ B_{in} + B_2\ *\ B_{in} = \bar{1}\ *\ (0) + \bar{1}\ *\ (1) + 0\ *\ (1) = 0\ *\ (0) + 0\ *\ (1) + 0\ *\ (1) = 0 + 0 + 0 = 0$
* **Result for Bit 2:**
    * Difference bit = 0
    * Borrow-out = 0

#### Final Result
Combining the difference bits from right to left, we get the final result:
**$D_2D_1D_0 = 010$**

In decimal, $010 = 2$, which is the correct answer for $5 - 3$. This example shows how a full subtractor works bit by bit to produce the final difference.

## Multiplication

### Rule

$$
0 \times 0 = 0  \\
1 \times 0 = 0  \\
0 \times 1 = 0  \\
1 \times 1 = 1  \\
$$

The process involves these steps:

1.  Align the numbers just like in decimal multiplication.
2.  Multiply the top number by each digit of the bottom number, starting from the right.
3.  For each multiplication, if the bottom digit is a **1**, the result is the top number. If the bottom digit is a **0**, the result is all 0s.
4.  Shift each successive result to the left by one position, just as you would in decimal multiplication.
5.  Add all the partial products together using binary addition rules.

### Example

1. $101 \times 10$ ($5 \times 2$ in decimal)

```
        1   0   1
            1   0
        ------------
0 ->    0   0   0
1 -> 1  0   1           (left shift 1 digit)
    ------------------------
     1  0   1   0   
```
$1010\ is\ 10$

2. $1101 \times 1011$ ($13 \times 11$)

```
                1   1   0   1
                1   0   1   1
            ------------------
c     1   1  1 
---------------------------------
1->             1   1   0   1
1->         1   1   0   1
0->     0   0   0   0
1->  1  1   0   1
    ------------------------------
    10  0   0   1   1   1   1            
```
$10001111\ is\ 143$

### How computers do?

Computers multiply binary numbers by leveraging the fundamental operations they are built for: **left shifting** and **addition**. They don't have separate hardware for multiplication like they do for addition. Instead, a multiplication operation is broken down into a series of shifts and additions.

Modern processors use more advanced algorithms, such as **Wallace tree multipliers**, which use a tree of adders to perform multiplication much faster by adding partial products in parallel.

## Division

$$
1 - 1 = 0 \\
1 - 0 = 1 \\
0 - 0 = 0 \\
0 - 1 = 1 (with\ borrow\ from\ next\ position)
$$

### Example

Let's divide $1010$ by $10$ ($10 \div 2$ in decimal).

1.  Set up the problem:
    ```
       _____
    10|1010
    ```
2.  Compare the divisor ($10$) with the first two digits of the dividend ($10$).
      * $10 \ge 10$, so the first digit of the quotient is **1**.
      * Subtract $10$ from $10$: $10 - 10 = 00$.
    ```
       _1
      _____
    10|1010
      -10
      ---
       00
    ```
3.  Bring down the next digit (1). The new number is $001$.
      * $10 > 001$, so the next digit of the quotient is **0**.
    ```
       _10
      ______
    10|1010
      -10
      ---
       001
    ```
4.  Bring down the next digit (0). The new number is $0010$.
      * $10 \ge 0010$, so the next digit of the quotient is **1**.
      * Subtract $10$ from $10$: $10 - 10 = 00$.
    ```
       _101
      _____
    10|1010
      -10
      ---
       0010
      -  10
      ----
         00
    ```

The quotient is $101$ and the remainder is $0$. In decimal, $10 \div 2 = 5$, and $101 = 5$. The result is correct.

### How computers do?

Computers perform division using a combination of **subtraction** and **right shifts**. They don't have a separate division unit. A standard algorithm is the **restoring division algorithm**, which works step-by-step to build the quotient.

## Bitwise

### and

#### Rule

$$
0 \& 0 = 0 \\
0 \& 1 = 0 \\
1 \& 0 = 0 \\
1 \& 1 = 1 \\
$$

The AND operation compares two bits and outputs a 1 only if both bits are 1. Otherwise, the output is 0.

#### Example


```
  1011  (11)
& 0110  (6)
-------
  0010  (2)
```

The AND operation is often used to clear specific bits or to mask a value to check if certain bits are set. For example, 1011 & 0010 will result in 0010 because only the second bit from the right is 1 in both numbers.

Think like this
1011 is the Flag, we would like to know wheather  0010 is present or not
```
    1011
&   0010
    ------
    0010
```
if result == check flag means flag is present

### or

#### Rule
$$
0 | 0 = 0 \\
0 | 1 = 1 \\
1 | 0 = 1 \\
1 | 1 = 1 \\
$$

The OR operation compares two bits and outputs a 1 if at least one of the bits is 1. The output is 0 only if both bits are 0.

#### Example
```
  1011  (11)
| 0110  (6)
-------
  1111  (15)
```

The OR operation is commonly used to set specific bits to 1. For example, 1011 | 0100 will result in 1111, setting the third bit from the right to 1.

### not

The NOT operation, also known as bitwise complement, inverts the bits of a single binary number. It changes every 0 to a 1 and every 1 to a 0.
```
~ 1011  (11)
-------
  0100  (4)
```

### xor

#### Rule
$$
0\ XOR\ 0 = 0 \\
0\ XOR\ 1 = 1 \\
1\ XOR\ 0 = 1 \\
1\ XOR\ 1 = 0 \\
$$
The XOR operation compares two bits and outputs a 1 if the bits are different. If they are the same, the output is 0.

XOR is used for many applications, including swapping two variables without a temporary variable and for simple encryption because of its property of self-cancellation: $A\ XOR\ B\ XOR\ B\ =\ A$.

```
  1011  (11)
^ 0110  (6)
-------
  1101  (13)
```


## shifting

These operations shift the bits of a number to the left or right.

### Left shift

Left Shift ($<<$): Shifts bits to the left, adding 0s to the right. It effectively multiplies the number by a power of 2.  
$101 << 1 = 1010 (5\ becomes\ 10)$ == 5 * (1 * 2) = 10    
$101 << 2 = 10100 (5\ becomes\ 20)$ == 5 * (2 * 2) = 20  


### Right shift

Right Shift (): Shifts bits to the right. It effectively divides the number by a power of 2. For unsigned numbers, 0s are added to the left.

Each position shifted to the right halves the number's value. For example, shifting a number right by one position is the same as dividing it by $2^1$(2)

$1010 << 1=101 (10\ becomes\ 5)$ == 10 / (1 * 2) = 5  
$10100 << 2=101 (20\ becomes\ 5)$ == 20 / (2 * 2) = 5  


# Floating IEEE 754

| Field     | Bit Range | Size     | Description                                                                 |
|-----------|-----------|----------|-----------------------------------------------------------------------------|
| Sign (S)  | 31        | 1 bit    | 0 for positive, 1 for negative                                              |
| Exponent (E) | 23–30  | 8 bits   | Stores the exponent in biased form (bias = 127)                            |
| Fraction (F) | 0–22   | 23 bits  | Stores the fractional part (significand/mantissa, with implicit leading 1) |


3.14159274 == 11.00100100001111110111


| Number  | Normalized Form|
| :---    | :---           |
| 3.14159 | 3.14159×$10^0$ |
| 123.45  | 1.2345×$10^2$  |
| 0.00456 | 4.56×$10^−3$   |


In binary (base 2) floating-point, the normalized form is required to have exactly one '1' to the left of the binary point.  All normalized numbers must start with 1..

So we no need to store the 1. -> 1, because every number will have 1

Normal = 11.00100100001111110111  
Normalized = 1.100100100001111110111

And the 1st bit is always 1 so we no need to store

s = 0
e = 1 -> $2^1$
fraction = 100100100001111110111

example:
-----------
Decimal: 5.0, Binary: 101.0    
Normalized Binary: $1.01 \times 2^2 $    
Sign (S): 0 (positive)  
Exponent(E): The actual exponent is 2. The biased exponent is 2+127=129. In binary, this is 10000001.   
Fraction (F): The part after the binary point is 01. We pad this with zeros to fill the 23 bits: 01000000000000000000000.

So, the IEEE 754 representation of 5.0 would be: `0 10000001 01000000000000000000000`


> [!TIP] 127 for single-precision.  
> The exponent is stored with a bias of 127.

What is a Bias?

The bias is a value added to the actual exponent to allow the representation of both positive and negative exponents without needing a separate sign bit for the exponent itself. This is particularly useful for simplifying hardware logic.

The bias of 127 is subtracted from the stored exponent value to get the true exponent.

`Actual Exponent=Stored Exponent − Bias`

For single-precision: Actual Exponent=Stored Exponent − 127

If stored exponent is 130, the actual exponent is 130−127=3. This means the number should be multiplied by $2^3$  
If stored exponent is 125, the actual exponent is 125−127=−2. This means the number should be multiplied by $2^(-2)$

This design choice ensures that the exponent is always a non-negative number within the 8-bit field, while still allowing the full range of both positive and negative exponents to be used.


## Airthmetic

### Addition

#### int with float

When adding an integer to a floating-point number, a computer first converts the integer into a floating-point format and then performs the standard floating-point addition.

Convert the Integer: The integer is converted into its equivalent floating-point representation. This involves:

1. Determining the sign of the integer.

2. Converting the integer's magnitude into its normalized binary form (e.g., 1010 becomes 1.010 x $2^3$).

3. Encoding the exponent (using the bias, e.g., 3 + 127 = 130) and the fraction (010).

Once the integer is in the floating-point format, the two numbers are added using float with float

#### float with float

Adding two floating-point numbers is more complex than adding integers because you must first align their exponents. It follows these steps:

1. Extract Components: Separate each number into its sign, exponent, and fraction. For a normalized single-precision number, remember to add the implicit leading `1` to the fraction.

2. Align Exponents: Find the number with the smaller exponent and shift its fraction to the right until its exponent matches the larger one. The number of places you shift is equal to the difference between the two exponents. Shifting right effectively divides the number by a power of two, which corresponds to increasing the exponent.

3. Add/Subtract Fractions: Add the fractions together. If the numbers have different signs, the operation becomes a subtraction.

4. Normalize the Result:
* If the sum of the fractions is too large (i.e., it creates a carry-out), shift the result's fraction one position to the right and increment the exponent by one.
* If the sum is too small (i.e., it has leading zeros), shift the fraction to the left and decrement the exponent until the leading 1 is in the correct position.

5. Round the Result: The final sum's fraction is often longer than the available bits, so it must be rounded according to the IEEE 754 standard's rounding rules (e.g., round to nearest even).

6. Re-assemble: Combine the final sign, exponent, and rounded fraction to form the final floating-point number.

#### Floating-Point Multiplication
To multiply two floating-point numbers, you follow these steps:

1. Multiply Signs: The sign of the result is the XOR of the two input signs.

2. Add Exponents: Add the two exponents and then subtract the bias from the result.

3. Multiply Fractions: Multiply the two fractions (including the implicit 1 for each).

4. Normalize: The result of the fraction multiplication may need to be shifted and the exponent adjusted to ensure it's in the normalized 1.xxxx format.

5. Round: The final fraction is rounded to fit the available bits.

#### Floating-Point Division
To divide two floating-point numbers, you follow a similar process:

1. Divide Signs: The sign of the result is the XOR of the two input signs.

2. Subtract Exponents: Subtract the divisor's exponent from the dividend's exponent, and then add the bias back to the result.

3. Divide Fractions: Divide the dividend's fraction by the divisor's fraction (including the implicit 1 for each).

4. Normalize: The result is normalized, and the exponent is adjusted accordingly.

5. Round: The final fraction is rounded.