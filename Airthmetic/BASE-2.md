## Addition

### Rules
```
0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 10  (which is 0 with a carry of 1 to the next bit)
```

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

```
1 - 1 = 0
1 - 0 = 1
0 - 1 = -1
0 - 0 = 0
----
10 - 1 = 1 (borrow)  from next higher value exchange for 2 groups
```

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

## Multiplication

## Division

## Bitwise

### and

### or

### not

### xor

## shifting
