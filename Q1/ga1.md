# Week 1 — Graded Assignment 1


---

### Q1 — Minimum Bits to Represent (32)₁₀ in Binary

**What is the minimum number of bits required to represent the number $(32)_{10}$ in binary?**

*(Numeric input)*

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{6}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Convert 32 to binary.**

$\displaystyle 32 = 2^5 = (100000)_2$

**Step 2 — Count the bits.**

The binary representation $100000$ has **6 bits**.

**Step 3 — Use the formula.**

The minimum number of bits to represent $N$ in binary is $\lfloor \log_2 N \rfloor + 1$:

$\displaystyle \lfloor \log_2 32 \rfloor + 1 = \lfloor 5 \rfloor + 1 = 5 + 1 = \boxed{6}$
</details>

---
### Q2 — Moore's Law: Transistor Count After 8 Years

**According to Moore's law, if a computer system has 2 million transistors today, approximately how many transistors would it have in 8 years?**

- ( ) 16 million transistors
- ( ) 8 million transistors
- ( ) 32 million transistors
- ( ) Cannot be determined

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 32 million transistors

#### ✏️ Step-by-Step Solution

**Step 1 — Recall Moore's Law.**

Moore's Law states that the number of transistors on a microchip **doubles approximately every 2 years**.

**Step 2 — Calculate the number of doublings.**

In 8 years, the number of 2-year intervals is:

$\displaystyle \frac{8 \text{ years}}{2 \text{ years/doubling}} = 4 \text{ doublings}$

**Step 3 — Apply the doubling formula.**

$\displaystyle \text{Transistors} = 2{,}000{,}000 \times 2^4 = 2{,}000{,}000 \times 16 = \boxed{32{,}000{,}000}$

$\displaystyle \boxed{32 \text{ million transistors}}$
</details>

---
### Q3 — Base Conversion: $(3451)_a = (1417)_b$

**If $(3451)_a = (1417)_b$, where $a$ and $b$ indicate the bases of the corresponding numbers, then what are the values of $a$ and $b$?**

- ( ) a = 7, b = 12
- ( ) a = 8, b = 10
- ( ) a = 9, b = 11
- ( ) a = 8, b = 11

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** a = 8, b = 11

#### ✏️ Step-by-Step Solution

**Step 1 — Note digit constraints.**

For a number in base $a$, all digits must be $< a$. In $(3451)_a$, the digits are 1, 3, 4, 5, so $a > 5$, i.e., $a \geq 6$.

For $(1417)_b$, digits are 1, 4, 7, so $b > 7$, i.e., $b \geq 8$.

**Step 2 — Try $a = 8$.**

$\displaystyle (3451)_8 = 3 \times 8^3 + 4 \times 8^2 + 5 \times 8 + 1 = 1536 + 256 + 40 + 1 = 1833$

**Step 3 — Try $b = 11$ with value 1833.**

$\displaystyle (1417)_{11} = 1 \times 11^3 + 4 \times 11^2 + 1 \times 11 + 7 = 1331 + 484 + 11 + 7 = 1833 \checkmark$

$\displaystyle \boxed{a = 8,\quad b = 11}$
</details>

---
### Q4 — Quadratic Equation: Find the Base

**The solutions to the quadratic equation $x^2 - 11x + 21 = 0$ are $x = 3$ and $x = 5$. What is the base of the numbers?**

*(Numeric input)*

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{7}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Understand the problem.**

The equation $x^2 - 11x + 21 = 0$ uses digits written in some base $b$. We need to find $b$ such that $x = 3$ and $x = 5$ are solutions when the digits are interpreted in base $b$.

**Step 2 — Convert the number representations to base 10.**

In base $b$:
- $11_b = 1 \cdot b + 1 = b + 1$
- $21_b = 2 \cdot b + 1 = 2b + 1$

**Step 3 — Use Vieta's formulas.**

For roots $r_1 = 3$ and $r_2 = 5$:
- Sum of roots: $r_1 + r_2 = 3 + 5 = 8 = b + 1 \Rightarrow b = 7$
- Product of roots: $r_1 \times r_2 = 3 \times 5 = 15 = 2b + 1 = 2(7) + 1 = 15 \checkmark$

$\displaystyle \boxed{b = 7}$
</details>

---
### Q5 — Highest Level of Abstraction in Computing Hierarchy

**What is the highest level of abstraction in the transformation hierarchy for computing systems?**

- ( ) Algorithms
- ( ) Programming Languages
- ( ) Computational Problem
- ( ) System Software

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** Computational Problem

#### ✏️ Step-by-Step Solution

**Step 1 — Recall the transformation hierarchy.**

The computing transformation hierarchy (from highest to lowest abstraction) is:

$\displaystyle \text{Computational Problem} \rightarrow \text{Algorithm} \rightarrow \text{Programming Language} \rightarrow \text{System Software} \rightarrow \text{Architecture} \rightarrow \text{Microarchitecture} \rightarrow \text{Hardware}$

**Step 2 — Identify the highest level.**

A **Computational Problem** is the most abstract — it specifies *what* needs to be computed without any concern for *how* it is computed.

$\displaystyle \boxed{\text{Computational Problem}}$
</details>

---
### Q6 — Convert Binary to Decimal: $(11001)_2$

**Convert $(11001)_2$ into decimal.**

*(Numeric input)*

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{25}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Expand using positional notation.**

$\displaystyle (11001)_2 = 1 \times 2^4 + 1 \times 2^3 + 0 \times 2^2 + 0 \times 2^1 + 1 \times 2^0$

$\displaystyle = 16 + 8 + 0 + 0 + 1 = \boxed{25}$
</details>

---
### Q7 — Largest 16-bit Binary Number in Decimal

**What is the decimal equivalent of the largest binary number possible to obtain with 16 bits?**

- ( ) 65789
- ( ) 65535
- ( ) 64321
- ( ) 65998

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 65535

#### ✏️ Step-by-Step Solution

**Step 1 — Find the largest 16-bit binary number.**

The largest 16-bit binary number has all bits set to 1:

$\displaystyle (1111\,1111\,1111\,1111)_2$

**Step 2 — Convert to decimal.**

$\displaystyle 2^{16} - 1 = 65536 - 1 = \boxed{65535}$
</details>

---
### Q8 — Voltage Interpretation: Illegal Voltage

**In a system if $V_L = 3.56$ and $V_H = 3.97$, then a voltage of 3.58 will be:**

- ( ) Interpreted as 0
- ( ) Interpreted as 1
- ( ) Interpreted as illegal voltage
- ( ) None of the above

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** Interpreted as illegal voltage

#### ✏️ Step-by-Step Solution

**Step 1 — Understand voltage thresholds.**

In digital logic:
- Voltages $\leq V_L$ are interpreted as logic **0**
- Voltages $\geq V_H$ are interpreted as logic **1**
- Voltages **between** $V_L$ and $V_H$ are in the **forbidden zone** (illegal / undefined)

**Step 2 — Check where 3.58 falls.**

$\displaystyle V_L = 3.56 < 3.58 < 3.97 = V_H$

The voltage 3.58 falls in the forbidden zone between $V_L$ and $V_H$.

$\displaystyle \boxed{\text{Interpreted as illegal voltage}}$
</details>

---
### Q9 — Base Conversion: 421 in Base 5 → Base ?

**The number 421 in base 5 system is equivalent to 157 in which base system?**

- ( ) 6
- ( ) 9
- ( ) 7
- ( ) 8

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 8

#### ✏️ Step-by-Step Solution

**Step 1 — Convert $(421)_5$ to decimal.**

$\displaystyle (421)_5 = 4 \times 5^2 + 2 \times 5^1 + 1 \times 5^0 = 100 + 10 + 1 = 111$

**Step 2 — Find base $b$ such that $(157)_b = 111$.**

$\displaystyle (157)_b = 1 \times b^2 + 5 \times b + 7 = 111$

$\displaystyle b^2 + 5b + 7 = 111 \implies b^2 + 5b - 104 = 0$

**Step 3 — Solve the quadratic.**

$\displaystyle b = \frac{-5 + \sqrt{25 + 416}}{2} = \frac{-5 + \sqrt{441}}{2} = \frac{-5 + 21}{2} = \frac{16}{2} = 8$

**Verify:** $(157)_8 = 64 + 40 + 7 = 111 \checkmark$

$\displaystyle \boxed{b = 8}$
</details>

---
### Q10 — Base 5 Number 223 in Hexadecimal

**If the representation of a number in base 5 is 223, then what will be its hexadecimal representation?**

- ( ) 1F
- ( ) 2E
- ( ) 40
- ( ) 53
- ( ) 3F

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 3F

#### ✏️ Step-by-Step Solution

**Step 1 — Convert $(223)_5$ to decimal.**

$\displaystyle (223)_5 = 2 \times 25 + 2 \times 5 + 3 = 50 + 10 + 3 = 63$

**Step 2 — Convert 63 to hexadecimal.**

$\displaystyle 63 = 3 \times 16 + 15 = (3F)_{16}$

$\displaystyle \boxed{(3F)_{16}}$
</details>

---
### Q11 — Base 6 Number 245 in Hexadecimal

**If the representation of a number in **base 6** is **245**, what will be its **hexadecimal** representation?**

- ( ) 5F
- ( ) 65
- ( ) 6B
- ( ) 71
- ( ) None of the above

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 65

#### ✏️ Step-by-Step Solution

**Step 1 — Convert $(245)_6$ to decimal.**

$\displaystyle (245)_6 = 2 \times 36 + 4 \times 6 + 5 = 72 + 24 + 5 = 101$

**Step 2 — Convert 101 to hexadecimal.**

$\displaystyle 101 = 6 \times 16 + 5 = (65)_{16}$

$\displaystyle \boxed{(65)_{16}}$
</details>
