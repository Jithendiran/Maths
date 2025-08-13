# Chapter 2: Arithmetic

## Addition
### What is addition?
Addition means putting things together. It answers the question: "How many in total?"
**Symbol : +**

### How it works?
Let's say you have 2 sticks. Each stick is represented as: `| |`  
Now you found one more stick: `|`  
Put them all together: `||` + `|` =`|||`  

In number way: `2+1 = 3`

### Read worl example  
* You have 2 pencils. Your friend gives you 4 more. Now you have 6 pencils.
* 3 apples in one basket, 5 in another → total 8 apples.

### Negative numbers
**Addition Sign Rules:**  
Operation Logic: Add means, add more gain or add more loss
| First Number (Start) | Second Number (Add) | Operation Logic        | Result Sign                | Example            |
| -------------------- | ------------------- | ---------------------- | -------------------------- | ------------------ |
| `+` (I have)         | `+` (I gain more)   | `+ + +` → Add values   | `+` (positive)             | `3 + 5 = +8`       |
| `+` (I have)         | `-` (I lose some)   | `+ + (-)` → Subtract   | Depends on which is bigger | `5 + (-2) = +3`    |
| `-` (I owe)          | `+` (I gain some)   | `- + +` → Subtract     | Depends on which is bigger | `(-2) + 5 = +3`    |
| `-` (I owe)          | `-` (I owe more)    | `- + (-)` → Add values | `-` (negative)             | `(-3) + (-4) = -7` |

### Carry over

If you get 10 or more pieces in any place, you MUST trade them for one of the next bigger pieces. This trade is the "carry-over."

#### Examples

1. No Carry
 1 + 5 = 6  
 `|` + `|||||` = `||||||`  

 ```
 0      1       2       3       4       5       6       7       8       9
        |                                       |
        +0      +1      +2      +3      +4      +5
        start                                   end
 ```
 
 Since we are following base-10 we have to symbol to represent six units
 the ones place can hold up to 9 (in base-10). Since 1+5 = 6, nothing needs to move to the next place.

2. Single carry over   
 7 + 5 = 12  
 `|||||||` + `|||||` = `||||||||||||`  

 ```
 1's
  0      1       2       3       4       5       6       7       8       9
                                                         |
                                                         +0     +1       +2   (still we have to add 3 units but we ran out of symbols
                                                                                Now move to next place value 10 and add the numbers there)
10's
  0       1       2       3      4       5       6       7       8       9   
 +3       +4      +5                 
                                                        

when we reach 9 + 1 -> we will reset the scale from 0 and add ten's place 1, in 10's place we can specify 0-9
 ```

 we have twelve units, we don't a single symbol to represent 12 so we are forming a group of with the next place value
 we have twelve units so we will trade 1 ten group unit for ten single units and remaining 2 extra   
 so it is 12   
 ```
 1    2    
10th 1's  0's
 ```

3. double carry 
99 + 1

```
1's
0      1       2       3       4       5       6       7       8       9
                                                                       |
                                                                      +0     

10's
0      1      2        3       4       5       6       7       8       9      
|
+1

adding +1 -> element of 1's place is full so it will exchange 1 group of ten for 10 units

we already have nine 10 group and new one more 10 group
so  90 + 10 = 100 

       place value
100    10     1     
-------------------
       carry
1      1
-------------------
0      9      9    (meaning have 9 group of 10's and 9 extra's)
0      0      1    (meaning have 0 group of 10's and 1 extra's)
--------------------
              0      (9 + 1) -> now we have ten single units so we can exchange it for 1 group of 10's, 
       0             we already gave nine ten groups and one more new ten group -> (9 + 1) -> we have ten 10 group, we can exchange it for single hendred unit
1                    we don't have any 100 group by adding one new hundred group we have one 100 group
                     
```


## Subtraction
### What is subtraction?
Subtraction means taking away. It answers: "How much is left?"  
**Symbol: -**  

### How it works?
If you have 5 sticks:  `|||||`  
And take away 2 sticks:`||`  
you're left with      :`  |||`  

In number way: `5-2 = 3`

### Read world example
* You had 5 chocolates. You gave 2 to your friend. Now you have 3 left.
* Bank account has ₹100, you spend ₹30 → ₹70 remains

### Negative numbers

Operation Logic: Sub means, take away gain or take away loss

| First Number (Start) | Second Number (Take Away) | Operation Logic      | Result Sign                | Example            |
| -------------------- | ------------------------- | -------------------- | -------------------------- | ------------------ |
| `+` (I have)         | `+` (I lose)              | `+ - +` → Subtract   | Depends on which is bigger | `5 - 2 = +3`       |
| `+` (I have)         | `+` (I lose more)         | `+ - +` → Subtract   | Depends on which is bigger | `2 - 5 = -3`       |
| `+` (I have)         | `-` (Remove a debt)       | `+ - (-)` → `+ +`    | Positive                   | `5 - (-3) = +8`    |
| `-` (I owe)          | `+` (Owe more)            | `- - +` → Add values | Negative                   | `(-3) - 2 = -5`    |
| `-` (I owe)          | `-` (Debt is cancelled)   | `- - (-)` → `- +`    | Depends on which is bigger | `(-5) - (-2) = -3` |

why `+ - (-)` → `+ +` ?  
 i have 5 rs, i owe 3 rupees, this can be written as +5, -3  
 here we are doing subract   
 (+5) - (-3) It is like subracting owing, so it is actually gain  
 +5 + 3 = 8

### Borrow

#### Examples

1. 9 - 2 = 7
```
0      1      2      3      4      5      6      7      8      9
                                                               |
                                                 -2<-- (-1) <--0
                                                 end           start
```

2. 13 - 9 = 4
```


1. in 1's place we have 3 - 9

0      1      2      3      4      5      6      7      8      9
|      |      |      |
-3    -2     -1      0 (start)


after 0's we can't do subtract any more, so we have to exchange 1 ten group for 10 single units
since we took and exchanged 1 ten group for 10 single units, we have to reduce 1 from ten group
now we have 0 ten group and 13 single units


0      1      2      3      4      5      6      7      8      9
|      |      |      |
-3    -2     -1      0 (start)

0      1      2      3      4      5      6      7      8      9     
                           -9     -8      -7    -6     -5     -4
                           (end)


10's   1's    

1      3      (1 group of 10's and 3 single units )

0      9      (0 group of 10's and 9 single units )
-------------------

9 is greater than 3, so we can't subtract, now exchange 10 single units from next higher place value
The next higher place value is 10's we have 1 ten group

10's   1's
0      13
0      9
------------
0      4
```

3. 23 - 9 = 14

```

10's   1's
2      3
0      9
-----------

9 is greater than 3, so we can't subtract, now exchange 10 single units from next higher place value
The next higher place value is 10's we have 2 ten group, so we can exchange 10 units for 1 ten group and reduce 1 ten group 

10's   1's
1      13
0      9
-----------
1      4
```

4. 100 - 1

```

100's  10's   1's
1      0      0
0      0      1
--------------------

1. we can't suubtract 1's place because 1 is greater than 0, we have to exchange, look for next place value
2. we have 0 group's of ten, so look for next place value
3. we have 1 group hundred's, so exchange it for 10 groups of ten's

100's  10's   1's
0      10     0

4. Now ten place value has value, exchage 1 group of ten's for 10 units 

100's  10's   1's
0      9     10

5. now do the subtract

100's  10's   1's
0      9      10
0      0      1
-------------------
       9      9
```

## Multiplication
### What is multiplication?
Multiplication means repeated addition. 
**Symbol : * or x**  

### How it works?
2 × 4 means adding 4 two times:  
`4 = | | | |`, `2 = | |`, for each `|` in 2, include all `|` in 4    
so,  
for 1st `|` in 2  
 = `| | | |`   
for 2nd `|` in 2  
 = `| | | |`  
Now add all them   
= `| | | |` + `| | | |` = `| | | | | | | |`  

In number way: `4x2 = 8`  

### Read worl example            
* 3 boxes with 5 mangoes each = 3 × 5 = 15 mangoes
* 4 weeks of 7 days = 4 × 7 = 28 days

### Negative numbers 
**Multiplication Sign Rules:**
| First Number (Direction) | Second Number (Repeat) | Movement Type                 | Final Result | Explanation                                             |
| ------------------------ | ---------------------- | ----------------------------- | ------------ | ------------------------------------------------------- |
| `+` (face right → +ve)   | `+` (repeat forward)   | Move forward                  | `+`          | Face +ve, walk forward → go right → result is positive  |
| `+` (face right → +ve)   | `−` (repeat backward)  | Move backward                 | `−`          | Face +ve, walk backward → go left → result is negative  |
| `−` (face left → −ve)    | `+` (repeat forward)   | Move backward                 | `−`          | Face −ve, walk forward → go left → result is negative   |
| `−` (face left → −ve)    | `−` (repeat backward)  | Move forward (double reverse) | `+`          | Face −ve, walk backward → go right → result is positive |

| Expression | Direction (First No.) | Steps (Second No.) | Path Taken    | Result |
| ---------- | --------------------- | ------------------ | ------------- | ------ |
| `+3 × +2`  | Face right            | 2 steps forward    | `0 → +3 → +6` | `+6`   |
| `+3 × −2`  | Face right            | 2 steps backward   | `0 → −3 → −6` | `−6`   |
| `−3 × +2`  | Face left             | 2 steps forward    | `0 → −3 → −6` | `−6`   |
| `−3 × −2`  | Face left             | 2 steps backward   | `0 → +3 → +6` | `+6`   |

| First Number (Amount) | Second Number (Times)        | Operation Logic                | Result Sign | Example        | Meaning                               |
| --------------------- | ---------------------------- | ------------------------------ | ----------- | -------------- | ------------------------------------- |
| `+` (Gain ₹3)         | `+` (2 times)                | `+ × +` → Gain repeated        | `+`         | `+3 × +2 = +6` | Gaining ₹3 two times                  |
| `+` (Gain ₹3)         | `-` (2 times loss)           | `+ × −` → Loss repeated        | `−`         | `+3 × −2 = −6` | Losing ₹3 two times                   |
| `−` (Owe ₹3)          | `+` (2 times)                | `− × +` → Owe repeated         | `−`         | `−3 × +2 = −6` | Borrowing ₹3 two times                |
| `−` (Owe ₹3)          | `−` (2 times debt cancelled) | `− × −` → Double cancel = Gain | `+`         | `−3 × −2 = +6` | Debt of ₹3 cancelled two times → gain |


**Memory trick**: Same signs = Positive, Different signs = Negative

### Shortcuts explain

#### Example

1. 12 * 2

```
              ten's         one's  
   2 ->        0             2
  12 ->        1             2  

```

`12 -> 10 + 2`, 1 group of 10 and 2 single units  

* Multiply one's place:  
    $2 \times 2$ = 4   (4 single units)

* Multiply ten's place:  
    $10 \times 2$ = 20 (2 group of tens)

Add the reults together `4 + 20 = 24`

2. 23 * 4
```
              ten's         one's  
   4 ->        0             4
  23 ->        2             3  

```

* Method 1

`23 -> 20 + 3`, 2 group of 10's and  3 single units

 Multiply one's place:  
   $3 \times 4$ is 12 (12 single units and we trade 1 group of 10's, so it will be  1 group of 10 and 2 single unit)

 Multiply ten's place:  
   $20 \times 4$ is 80 (80 single units and we can trade for 8 group of 10's and 0 single unit )

Add the results together = `12 + 80 = 92`

* Method 2

```
                     2    3    *     4
                     -------------------
carry:
  1's:              
 10's:                    
```
1. Multiply 1's $3 \times 4 = 12$ write 2 in 1's place and 1 in 10's place.  

```
                     2    3    *     4
                     -------------------
carry:
  1's:               1    2  
 10's:                    
```

2. Multiply 10's, Since it is 10's place we have to start from 10's place not from 1's $2 \times 4 = 8$  write 8 in 10's group  
   $2 \times 4 = 8$ is single 8, why we have to write in 10's?  This is because we are multiplying 2 group of 10's which is equal $20 \times 4 = 80$, for shortcut multiplicaton we removed 0, 
```
                     2    3    *     4
                     -------------------
carry:
  1's:               1    2  
 10's:               8    0 -> this 0 is place holder for 10's
```   

Now add them

```
                     2    3    *     4
                     -------------------
carry:
  1's:               1    2  
 10's:               8    0 
                     --------------------
                     9    2
```

3. 34 * 46

* Method 1
```
             10's    1's
       34 -> 3   +   4      
       46 -> 4   +   6

34 -> 30 + 4
46 -> 40 + 6

        (30 + 4) x (40 + 6 )
6  
       1. 4  * 6 =   24
       2. 30 * 6 =  180
40
       1. 4  * 40 =  160
       2. 30 * 40 = 1200
        -------------
        simplify (30 * 40)
                        
                      1000's 100's  10's    1's
          1. 30 * 0 =               0      0               // 0 is 1's place, so started with 1's 
          2. 30 * 4 =  1     2      0                      // 4 is from 10's place
``` 
Add them all together
```

              2      4
       1      8      0
       1      6      0
1      2      0      0
-----------------------

carry
       1
-------------------------
1      4+1     6      4       

1      5      6      4
```
 
 * Method 2
```
       3      4      x      4      6
       ------------------------------
``` 
- Multiply with 1's $6 \times 4 = 2 4 (1's)$ and $6 \times 3 = 18(10's)$

```

       3      4      x      4      6
       ------------------------------

              1000's 100's  10's   1
                            2      4      (6 x 4)
                     1      8             (6 x 3)
       ------------------------------         

```

- Multiply with 10's $4 \times 4 = 16$ and $4 \times 3 = 12$

```

       3      4      x      4      6
       ------------------------------

              1000's 100's  10's   1
                            2      4      (6 x 4)     (4 is 1's and 6 is 1's, so start from 1's)
                     1      8             (6 x 3)     (3 is 10's and 6 is 1's, so start from 10's)  
                     1      6             (4 x 4)     (4 is 10's and 4 is 1's, so start from 10's)
              1      2                    (4 x 3)     (4 is 10's and 3 is 10's, so start from 100's) 
       ------------------------------     
carry:
                     1
       ------------------------------
              1      5      6     4
             
```

## Division
### What is division?
Division means splitting or grouping. It answers:
* How many groups?
* How many in each group?  
**Symbol : / or %**

### How it works?
Say you have 6 sticks: `| | | | | | |`  
You want to divide them into 2 equal groups. You put one stick in each group repeatedly:  
```
Group 1: | | |
Group 2: | | |
```
so: `6 / 2 = 3`  
Say you have 7 sticks: `| | | | | | | |`  

A box can hold max of 2 sticks, how many pair it makes?

`[||], [||], [||], [|]`  
3 box is full and 1 box is half, so 3.5  
so: `7 / 2 = 3.5 or 3 1/2`  

$$\frac{Total\ object}{Group\ size} = No.of.groups $$

### Read worl example        
* Sharing 12 pizzas among 4 people, each gets 3 pizzas     
* 100 km journey in 2 hours, speed is 50 km/hour  

### Negative numbers 

**Division Sign Rules:**

End / step direction = facing direction

| First Number (Result/End) | Second Number (Step Size) | Inverse Movement             | Final Result | Explanation                                           |
| ------------------------- | ------------------------- | ---------------------------- | ------------ | ----------------------------------------------------- |
| `+` (at +6)               | `+` (step forward)        | Faced right, walked forward  | `+`          | Got to +6 by moving forward → must’ve faced right (+) |
| `+` (at +6)               | `−` (step backward)       | Faced left, walked backward  | `−`          | Got to +6 by moving backward → must’ve faced left (−) |
| `−` (at −6)               | `+` (step forward)        | Faced left, walked forward   | `−`          | Got to −6 by forward steps → must’ve faced left (−)   |
| `−` (at −6)               | `−` (step backward)       | Faced right, walked backward | `+`          | Got to −6 by backward steps → must’ve faced right (+) |


| Expression | End Point (1st No.) | Step Size (2nd No.) | Direction Faced | Step Direction | Path Taken         | Result |
| ---------- | ------------------- | ------------------- | --------------- | -------------- | ------------------ | ------ |
| `+6 ÷ +2`  | `+6`                | +2                  | Face Right      | Forward        | `0 → +2 → +4 → +6` | `+3`   |
| `+6 ÷ −2`  | `+6`                | −2                  | Face Left       | Backward       | `0 ← −2 ← −4 ← −6` | `−3`   |
| `−6 ÷ +2`  | `−6`                | +2                  | Face Left       | Forward        | `0 → −2 → −4 → −6` | `−3`   |
| `−6 ÷ −2`  | `−6`                | −2                  | Face Right      | Backward       | `0 ← +2 ← +4 ← +6` | `+3`   |



| Division  | End Position | Step Size | Facing Direction | Step Direction | Result |
| --------- | ------------ | --------- | ---------------- | -------------- | ------ |
| `+6 ÷ +2` | +6           | Forward   | Right            | Forward        | `+3`   |
| `+6 ÷ −2` | +6           | Backward  | Left             | Backward       | `−3`   |
| `−6 ÷ +2` | −6           | Forward   | Left             | Forward        | `−3`   |
| `−6 ÷ −2` | −6           | Backward  | Right            | Backward       | `+3`   |

| **Total (What I Have/Owe)** | **Each Share (Per Group)**    | **Operation Logic**          | **Result Sign** | **Example**    | **Meaning**                                                          |
| --------------------------- | ----------------------------- | ---------------------------- | --------------- | -------------- | -------------------------------------------------------------------- |
| `+6` (I got ₹6)             | `+2` (Each gave ₹2)           | `+ ÷ +` → Receive ₹2 each    | `+3`            | `+6 ÷ +2 = +3` | I got ₹6, from each I received ₹2 → 3 times I received               |
| `+6` (I got ₹6)             | `−2` (Each debt cancelled ₹2) | `+ ÷ −` → Debt canceled      | `−3`            | `+6 ÷ −2 = −3` | I got ₹6, and each debt cancel was worth ₹2 → 3 cancels = total gain |
| `−6` (I owe ₹6)             | `+2` (Each repay ₹2)          | `− ÷ +` → Repay in steps     | `−3`            | `−6 ÷ +2 = −3` | I owe ₹6, repaying ₹2 each time → 3 times repaid                     |
| `−6` (I owe ₹6)             | `−2` (Cancel ₹2 per step)     | `− ÷ −` → Cancel debt groups | `+3`            | `−6 ÷ −2 = +3` | I owed ₹6, canceled ₹2 per time → 3 cancels = fully cleared          |


**Memory trick**: Same signs = Positive, Different signs = Negative
