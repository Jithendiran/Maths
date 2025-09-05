# How Computers Represent Numbers

## 1. What Is a Negative Number?

In mathematics, a **negative number** is a value that is **less than zero**. Negative numbers are typically used to represent loss, debt, direction, or any quantity that is opposite in nature to a positive one.

For example:

* The negative of 5 is written as `-5`.
* When you add `5` and `-5`, the result is `0`, because they cancel each other out.

$$
5 + (-5) = 0
$$

## 2. Representing Negative Numbers Using the `-` Symbol

In traditional notation, we use a **minus sign (`-`)** to indicate negative values. This works well for human-readable math, but in computers, it's not that straightforward.

Early computers (and modern hardware at the low level) do **not** actually have a physical representation of the `-` sign. Instead, they use **binary patterns** and mathematical tricks to represent and compute with negative numbers.

---

## 3. Representing Negative Numbers *Without* the `-` Symbol

To perform arithmetic without using the `-` symbol, we use a concept called **complement systems**. The core idea is:

> Represent negative numbers in such a way that addition still works — no need for separate subtraction logic.

Let's understand this concept by building from decimal numbers before moving to binary.

---

## 4. Decimal System Example (Base 10)

Suppose we are working in **base 10** with **one-digit numbers** only (i.e., values from 0 to 9). The goal is to find a way to represent negative numbers **without** using the `-` sign.

### Goal:

Find a number that, when added to a given number, results in `0` — or a value where we can **ignore the carry** and get `0`.

Since we're limited to positive digits only (0–9), we define a **complement**:

> A number’s "negative" is the value that, when added to it, gives **10**, and we **ignore the carry** (i.e., just keep the last digit `0`).

### Complement Table (1-digit system)

| Number | What to Add to Get 10 | Interpreted as Negative |
| ------ | --------------------- | ----------------------- |
| 0      | 10 -> 0               | 0                       |
| 1      | 9                     | 9                       |
| 2      | 8                     | 8                       |
| 3      | 7                     | 7                       |
| 4      | 6                     | 6                       |
| 5      | 5                     | 5                       |
| 6      | 4                     | 4                       |
| 7      | 3                     | 3                       |
| 8      | 2                     | 2                       |
| 9      | 1                     | 1                       |

This approach works because:

$$
4 + 6 = 10 \Rightarrow 0 \quad (\text{drop carry})
$$

$$
2 + 8 = 10 \Rightarrow 0
$$

This concept is called the **10's Complement**, and it allows us to represent negative numbers by calculating the complement and treating addition as our only operation.

---

## 5. Multi-Digit Numbers: A Problem Appears

Let’s try with a multi-digit number: `8623`.

### Naive Approach (Digit-wise 10's complement)

Using the same logic for each digit:

* 8 → 2
* 6 → 4
* 2 → 8
* 3 → 7

This gives us:
**Complement of 8623 → 2487**

Now, add:

$$
8623 + 2487 = 11110 \Rightarrow \text{Drop carry} \Rightarrow 1110 \quad (\text{Incorrect})
$$

### Why It Fails:

Because each digit’s carry propagates to the next digit, and simple digit-wise complements do not account for this.

---

## 6. The Correct Way: 9’s and 10’s Complement

Instead of adding up to `10` for each digit, we use **9's complement** followed by adding `1`.

### Step 1: Find 9's Complement

Subtract each digit from 9:

* 8 → 1
* 6 → 3
* 2 → 7
* 3 → 6

So the 9's complement of `8623` is `1376`.

### Step 2: Add 1 (This gives us 10's complement)

$$
1376 + 1 = 1377
$$

Now, verify:

$$
8623 + 1377 = 10000 \Rightarrow \text{Drop carry} \Rightarrow 0000
$$

This works correctly. The number `1377` behaves as the **negative of 8623**, and the sum is effectively zero.

---

## 7. Why Is This Useful?

In computers, the hardware typically only performs **addition**. To support subtraction and negative numbers efficiently, we need a way to make **subtraction look like addition**.

The complement system allows this by:

* Representing negative numbers as complements of positive ones.
* Avoiding extra logic for subtraction.
* Simplifying hardware design.

This idea is used not only in decimal systems historically but also in **binary systems**, where the same principle is applied with **1’s and 2’s complements**.

---

## 8. Subtracting Multi-Digit Numbers Using 10’s Complement

Let’s apply the same 10’s complement trick to perform subtraction like a computer — using **only addition**.

We want to compute:

> **A - B**

Instead of subtracting directly, we:

1. Take the **10’s complement** of `B`.
2. **Add** it to `A`.
3. If there's a **carry**, drop it — the result is **positive**.
4. If there's **no carry**, take the **10’s complement** of the result — and the final answer is **negative**.

---

### Example 1: `8652 - 2739` using 10’s complement

We want:

$$
8652 - 2739 = ?
$$

### Step 1: Find 10’s complement of `2739`

**a. 9’s complement (subtract each digit from 9)**:

| Digit | 9 - Digit |
| ----- | --------- |
| 2     | 7         |
| 7     | 2         |
| 3     | 6         |
| 9     | 0         |

So:

```
9's complement of 2739 → 7260
```

**b. Add 1 to get 10's complement**:

```
7260 + 1 = 7261
```

---

### Step 2: Add to 8652

```
8652 + 7261 = 15913
```

### Step 3: Drop the carry (the leading 1)

```
5913
```

Final Answer: `8652 - 2739 = 5913`

---

### Example 2: `2739 - 8652` using 10’s complement

Let’s reverse it:

$$
2739 - 8652 = ?
$$

We expect a **negative** result.

### Step 1: Find 10’s complement of `8652`

**a. 9’s complement**:

| Digit | 9 - Digit |
| ----- | --------- |
| 8     | 1         |
| 6     | 3         |
| 5     | 4         |
| 2     | 7         |

```
9’s complement of 8652 → 1347
```

**b. Add 1**:

```
1347 + 1 = 1348
```

---

### Step 2: Add to 2739

```
2739 + 1348 = 4087
```

### Step 3: No carry → Take 10’s complement of 4087

**a. 9's complement**:

| Digit | 9 - Digit |
| ----- | --------- |
| 4     | 5         |
| 0     | 9         |
| 8     | 1         |
| 7     | 2         |

```
9's complement → 5912
```

**b. Add 1**:

```
5912 + 1 = 5913
```

Final Answer: `-5913`


# Binary Number Representation in Computers

In the previous section, we explored how to represent negative numbers without using the `-` symbol using **complement systems** in the **decimal system**. Now, let’s extend the same idea to the **binary system**, which is the core of how modern computers operate.

---

## 1. Unsigned Binary Numbers

A binary number with `n` bits can represent values from `0` to `2ⁿ - 1`.
For example, with **4 bits**, we can represent:

$$
\text{Range: } 0000 \text{ (0)} \text{ to } 1111 \text{ (15)}
$$

But this range only supports **positive integers** (unsigned numbers). To support **negative numbers**, we need to introduce a way to indicate **sign** in binary.

---

## 2. Signed Binary Numbers

To represent both **positive and negative** numbers, we reserve the **most significant bit (MSB)** as the **sign bit**:

* `0` → Positive
* `1` → Negative

With this setup, the remaining `n-1` bits are used to store the magnitude of the number.

There are several methods to represent signed binary numbers:

* **Signed Magnitude**
* **1’s Complement**
* **2’s Complement**

Each method offers different trade-offs in terms of range, arithmetic simplicity, and uniqueness of zero representation.

---

## 3. Methods to Represent Signed Binary Numbers

### 3.1 Signed Magnitude

In **signed magnitude representation**:

* The **MSB** is the sign bit.
* Remaining **`n-1` bits** represent the absolute value (magnitude).

#### Example (4-bit system):

* `0101` → +5
* `1101` → -5

#### Range:

* Maximum positive: $2^{n-1} - 1$
* Minimum negative: $-(2^{n-1} - 1)$

#### Limitation:

* **Two representations of 0**:

  * `0000` → +0
  * `1000` → -0
* Arithmetic operations (like addition and subtraction) are **complex**, because sign and magnitude must be handled separately.

---

### 3.2 1’s Complement

In **1’s complement representation**:

* Positive numbers remain unchanged.
* Negative numbers are represented by **inverting all bits** of the corresponding positive value (i.e., applying a bitwise NOT).

#### Example (4-bit system):

* +5: `0101`
* -5: `1010` (1’s complement of `0101`)

#### Range:

* Maximum positive: $2^{n-1} - 1$
* Minimum negative: $-(2^{n-1} - 1)$

#### Limitation:

* Still has **two representations of 0**:

  * `0000` → +0
  * `1111` → -0
* Arithmetic operations require an extra step: if there's a carry out of the MSB, it must be **added back** (called *end-around carry*).

---

### 3.3 2’s Complement

The **2’s complement** method is the most widely used way of representing signed integers in binary systems.

* Positive numbers: unchanged
* Negative numbers:

  * First, compute the **1’s complement** (invert all bits)
  * Then, **add 1**

#### Example (4-bit system):

Represent `-5`:

1. Start with `+5` → `0101`
2. 1’s complement → `1010`
3. Add 1 → `1011` → this is `-5` in 2's complement

#### Range:

* Maximum positive: $2^{n-1} - 1$
* Minimum negative: $-2^{n-1}$

$$
\text{For 4 bits: Range = } -8 \text{ to } +7
$$

#### Advantages:

* **Only one representation of 0** (`0000`)
* Arithmetic operations like addition and subtraction are **simplified**
* Widely used in modern processors due to hardware efficiency

---

## 4. Summary of Signed Binary Representations

| Method           | Zero Representations | Range                              | Arithmetic Complexity | Notes                               |
| ---------------- | -------------------- | ---------------------------------- | --------------------- | ----------------------------------- |
| Signed Magnitude | Two (`+0`, `-0`)     | $\pm(2^{n-1} - 1)$                 | Complex               | Easy to understand, hard to compute |
| 1’s Complement   | Two (`+0`, `-0`)     | $\pm(2^{n-1} - 1)$                 | Medium                | Requires end-around carry           |
| 2’s Complement   | One (`0`)            | $-2^{n-1} \text{ to } 2^{n-1} - 1$ | Simple                | Standard in modern systems          |

---

## 5. Why 2’s Complement Is Preferred

* Eliminates dual representation of zero
* Simplifies addition and subtraction
* Enables use of the same hardware circuitry for both signed and unsigned operations
* Efficient and reliable, especially at the hardware level

---

## Final Note

The binary complement system — especially **2’s complement** — directly mirrors the idea of **10’s complement** in the decimal system discussed earlier. It reflects a fundamental principle in computing: simplify complex operations (like subtraction or negativity) by translating them into **addition** and using **bitwise manipulation**.

This elegant mathematical trick is at the heart of modern computing arithmetic.
