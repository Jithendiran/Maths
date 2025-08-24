## Addition
1.
 - 0 + 1 = 1
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


## Subtraction

Rule  

```
1 - 1 = 0
1 - 0 = 1
0 - 1 = -1
0 - 0 = 0
----
10 - 1 = 1 (borrow)  from next higher value exchange for 2 groups
```

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
as a result we get  11010, which is wrong

## Multiplication

## Division

## Bitwise

### and

### or

### not

### xor

## shifting
