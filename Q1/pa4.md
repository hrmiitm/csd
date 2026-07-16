# Week 4 — Practice Assignment 4
---

### Q1 — Two-Bit Comparator Input Combinations for A < B
**The output of a 2-bit comparator is high whenever input A is less than input B. For how many input combinations will the output be high in this circuit?**
- ( ) 4
- ( ) 6
- ( ) 5
- ( ) 7

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 6

#### ✏️ Step-by-Step Solution

**Step 1 — Identify the inputs and total combinations.**
A 2-bit comparator has two 2-bit inputs:
- $A = A_1 A_0$
- $B = B_1 B_0$
Each 2-bit input can represent values from $0$ to $3$ in decimal: $\{0, 1, 2, 3\}$.
The total number of input combinations is $2^2 \times 2^2 = 4 \times 4 = 16$ combinations.
**Step 2 — Count the combinations where $A < B$.**
Let's list the possible values of $B$ and count the valid values of $A$ that satisfy $A < B$:
- If $B = 0$: No value of $A$ is $< 0$ $\implies$ **0 combinations**
- If $B = 1$: $A \in \{0\}$ $\implies$ **1 combination** ($A=0, B=1$)
- If $B = 2$: $A \in \{0, 1\}$ $\implies$ **2 combinations** ($A=0, B=2$ and $A=1, B=2$)
- If $B = 3$: $A \in \{0, 1, 2\}$ $\implies$ **3 combinations** ($A=0, B=3$, $A=1, B=3$, and $A=2, B=3$)
**Step 3 — Sum the combinations.**
$\displaystyle \text{Total Combinations} = 0 + 1 + 2 + 3 = \boxed{6}$
</details>

---
### Q2 — Minimized Expression for 2-Bit Comparator (X < Y)
**Consider that $X = X_1X_0$ and $Y = Y_1Y_0$ are the two inputs to a 2-bit comparator circuit. What is the minimized expression for the Boolean function that provides a high output when $X < Y$?**
- ( ) $\overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0 + \overline{X_0}Y_1Y_0$
- ( ) $\overline{X_1}Y_1 + \overline{X_1}X_0Y_0 + \overline{X_0}Y_1Y_0$
- ( ) $\overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0 + X_0Y_1Y_0$
- ( ) $X_1\overline{Y_1} + X_1X_0\overline{Y_0} + X_0\overline{Y_1}\ \overline{Y_0}$

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** $\overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0 + \overline{X_0}Y_1Y_0$

#### ✏️ Step-by-Step Solution

**Step 1 — Analyze the condition $X < Y$.**
For $X = X_1 X_0$ and $Y = Y_1 Y_0$, the condition $X < Y$ is satisfied if:
1. The MSB of $X$ is less than the MSB of $Y$:
   $\displaystyle X_1 = 0 \text{ and } Y_1 = 1 \implies \overline{X_1}Y_1$
2. The MSBs are equal, and the LSB of $X$ is less than the LSB of $Y$:
   $\displaystyle (X_1 \odot Y_1) \cdot \overline{X_0}Y_0 = (X_1 Y_1 + \overline{X_1}\ \overline{Y_1}) \cdot \overline{X_0}Y_0$
**Step 2 — Sum and simplify the terms.**
$\displaystyle f(X < Y) = \overline{X_1}Y_1 + (X_1 Y_1 + \overline{X_1}\ \overline{Y_1}) \cdot \overline{X_0}Y_0$
$\displaystyle = \overline{X_1}Y_1 + X_1 Y_1 \overline{X_0} Y_0 + \overline{X_1}\ \overline{Y_1}\ \overline{X_0} Y_0$
Combine the first and third terms:
$\displaystyle \overline{X_1}Y_1 + \overline{X_1}\ \overline{Y_1}\ \overline{X_0} Y_0 = \overline{X_1} \left( Y_1 + \overline{Y_1}\ \overline{X_0}Y_0 \right)$
Using the identity $A + \overline{A}B = A + B$:
$\displaystyle = \overline{X_1} \left( Y_1 + \overline{X_0}Y_0 \right) = \overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0$
Now combine this result with the second term:
$\displaystyle f(X < Y) = \overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0 + X_1 Y_1 \overline{X_0} Y_0$
Combine the first and third terms:
$\displaystyle \overline{X_1}Y_1 + X_1 Y_1 \overline{X_0} Y_0 = Y_1 \left( \overline{X_1} + X_1 \overline{X_0}Y_0 \right)$
Using $A + \overline{A}B = A + B$:
$\displaystyle = Y_1 \left( \overline{X_1} + \overline{X_0}Y_0 \right) = \overline{X_1}Y_1 + \overline{X_0}Y_1Y_0$
Substitute this back to get the fully minimized expression:
$\displaystyle f(X < Y) = \boxed{\overline{X_1}Y_1 + \overline{X_1}\ \overline{X_0}Y_0 + \overline{X_0}Y_1Y_0}$
</details>

---
### Q3 — Stuck-At Fault in Decimal-to-BCD Encoder
**Consider the circuit of the decimal to BCD encoder given below. The OR gate $A_2$ fails with the output terminal as always high. How many output codes will be affected due to this?**
![Encoder Circuit](assets/pa4_w4pa3.png)
- ( ) 3
- ( ) 5
- ( ) 0
- ( ) 6

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 6

#### ✏️ Step-by-Step Solution

**Step 1 — Understand BCD Encoder output representation.**
A decimal-to-BCD encoder takes 10 inputs ($Y_0$ to $Y_9$) and produces 4 BCD output bits ($A_3, A_2, A_1, A_0$).
The normal output for $A_2$ is:
$\displaystyle A_2 = Y_4 + Y_5 + Y_6 + Y_7$
Thus, $A_2 = 1$ for inputs $4, 5, 6, 7$, and $A_2 = 0$ for inputs $0, 1, 2, 3, 8, 9$.
**Step 2 — Identify the effect of $A_2$ stuck-at-1.**
When the output terminal of $A_2$ fails and is always high ($A_2 = 1$):
- For inputs where $A_2$ was originally $1$ (inputs $4, 5, 6, 7$), the output remains correct.
- For inputs where $A_2$ was originally $0$ (inputs $0, 1, 2, 3, 8, 9$), the output code will be incorrect because $A_2$ becomes $1$.
The affected inputs are $\{0, 1, 2, 3, 8, 9\}$.
Counting these inputs gives:
$\displaystyle \text{Total Affected Codes} = \boxed{6}$
</details>

---
### Q4 — Multiplexer Implementation of Logic Circuit
**Consider the circuit shown below.**
*(Assuming a 3-variable logic circuit implementing a boolean function)*
**Consider that we have inputs A, B, C, and their complements. Find the minimum number of 4:1 multiplexers required to implement the above logic diagram.**

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{1}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Recall Shannon's Expansion Theorem.**
Any 3-variable Boolean function $f(A, B, C)$ can be expanded about two variables (e.g., $A$ and $B$) using Shannon's expansion theorem:
$\displaystyle f(A, B, C) = \overline{A}\ \overline{B} \cdot f(0, 0, C) + \overline{A}B \cdot f(0, 1, C) + A\overline{B} \cdot f(1, 0, C) + AB \cdot f(1, 1, C)$
**Step 2 — Map to a 4:1 multiplexer structure.**
A 4:1 multiplexer selects one of 4 inputs based on two select lines. By choosing $A$ and $B$ as the select lines:
- The MUX outputs: $Y = \overline{S_1}\ \overline{S_0} I_0 + \overline{S_1} S_0 I_1 + S_1 \overline{S_0} I_2 + S_1 S_0 I_3$.
- By setting $S_1 = A$, $S_0 = B$ and inputting the terms $f(0, 0, C), f(0, 1, C), f(1, 0, C), f(1, 1, C)$ (which evaluate to either $0$, $1$, $C$, or $\overline{C}$) to $I_0, I_1, I_2, I_3$, we can implement any 3-variable function using a single 4:1 MUX.
Thus, only **1** 4:1 multiplexer is required.
</details>

---
### Q5 — Boolean Expression Implemented by MUX Circuit
**Consider the circuit shown below.**
![Circuit for Q5](assets/pa4_w4pa5.png)
**The Boolean expression Y implemented by the circuit is:**
- ( ) $A + B + C$
- ( ) $A \odot B \odot C$
- ( ) $A \oplus B \oplus C$
- ( ) None of the above

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** $A \oplus B \oplus C$

#### ✏️ Step-by-Step Solution

**Step 1 — Trace the output of the first MUX (left).**
- Select line: $C$
- Inputs: $I_0 = 1$, $I_1 = 0$
- Output:
$\displaystyle G_1 = \overline{C}(1) + C(0) = \overline{C}$
**Step 2 — Trace the outputs of the middle MUXes.**
- **Upper MUX**:
  - Select line: $B$
  - Inputs: $I_0 = C$, $I_1 = G_1 = \overline{C}$
  - Output:
$\displaystyle G_{\text{top}} = \overline{B}C + B\overline{C} = B \oplus C$
- **Lower MUX**:
  - Select line: $B$
  - Inputs: $I_0 = G_1 = \overline{C}$, $I_1 = C$
  - Output:
$\displaystyle G_{\text{bottom}} = \overline{B}\cdot\overline{C} + BC = B \odot C = \overline{B \oplus C}$
**Step 3 — Trace the output of the final MUX (right).**
- Select line: $A$
- Inputs: $I_0 = G_{\text{top}} = B \oplus C$, $I_1 = G_{\text{bottom}} = \overline{B \oplus C}$
- Output:
$\displaystyle Y = \overline{A}(B \oplus C) + A(\overline{B \oplus C}) = A \oplus (B \oplus C) = \boxed{A \oplus B \oplus C}$
</details>

---
### Q6 — Canonical POS Expression from 4:1 MUX
**Consider the circuit shown below.**
![Circuit for Q6](assets/pa4_w4pa6.png)
**The canonical product of sum (POS) expression f(A, B, C) is:**
- ( ) $\pi(1, 6, 7)$
- ( ) $\pi(1, 2, 6, 7)$
- ( ) $\pi(0, 3, 4, 5)$
- ( ) $\pi(0, 4, 5)$

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** $\pi(0, 3, 4, 5)$

#### ✏️ Step-by-Step Solution

**Step 1 — Analyze the multiplexer connections.**
A 4:1 multiplexer with select lines $A, B$ has output:
$\displaystyle f(A, B, C) = \overline{A}\ \overline{B} I_0 + \overline{A}B I_1 + A\overline{B} I_2 + AB I_3$
From the circuit diagram, the inputs are connected such that:
- $I_0 = C \implies \overline{A}\ \overline{B}C$ (minterm 1)
- $I_1 = \overline{C} \implies \overline{A}B\overline{C}$ (minterm 2)
- $I_2 = \overline{C} \implies A\overline{B}\ \overline{C}$ (minterm 6)
- $I_3 = C \implies ABC$ (minterm 7)
**Step 2 — List minterms and maxterms.**
The sum of products (SOP) form is:
$\displaystyle f(A, B, C) = \sum(1, 2, 6, 7)$
The canonical Product of Sums (POS) form uses maxterms corresponding to the remaining indices where $f = 0$ (indices $\{0, 3, 4, 5\}$):
$\displaystyle f(A, B, C) = \boxed{\pi(0, 3, 4, 5)}$
</details>

---
### Q7 — Number of 2-Input MUXes for $2^8$-Input MUX
**How many 2 input multiplexers are required to construct a $2^8$ input multiplexer?**
- ( ) 512
- ( ) 256
- ( ) 255
- ( ) 1023

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 255

#### ✏️ Step-by-Step Solution

**Step 1 — Understand hierarchical multiplexer trees.**
A $N$-input multiplexer selects 1 output out of $N$ inputs.
If we build this structure using 2:1 multiplexers:
- Each 2:1 MUX reduces the number of intermediate signal lines by 1 (takes 2 inputs, outputs 1).
- To reduce $N$ inputs down to a single output line, we must perform exactly $N - 1$ reductions.
**Step 2 — Calculate for $N = 2^8$.**
Given $N = 2^8 = 256$:
$\displaystyle \text{MUXes Required} = 256 - 1 = \boxed{255}$
</details>

---
### Q8 — Number of 2-to-4 Decoders for 7-to-128 Decoder
**How many 2-to-4 line decoders with enable inputs are required to construct a 7-to-128 line decoder without using any other logic gates?**
- ( ) 43
- ( ) 42
- ( ) 40
- ( ) 32

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 42

#### ✏️ Step-by-Step Solution

**Step 1 — Calculate decoder layer requirements.**
To construct a 7-to-128 decoder using 2-to-4 decoders (which have 4 outputs each):
- **Final Layer**: Needs to output 128 lines. Since each decoder has 4 outputs:
  $\displaystyle N_{\text{final}} = \frac{128}{4} = 32 \text{ decoders}$
- **Second Layer**: Needs to drive the enable inputs of the 32 decoders in the final layer. Since each decoder has 4 outputs:
  $\displaystyle N_{\text{second}} = \frac{32}{4} = 8 \text{ decoders}$
- **Third Layer**: Needs to drive the enable inputs of the 8 decoders in the second layer. Since each decoder has 4 outputs:
  $\displaystyle N_{\text{third}} = \frac{8}{4} = 2 \text{ decoders}$
- **First Layer (Top)**: Needs to drive the enable inputs of the 2 decoders in the third layer. A single decoder can drive up to 4 inputs:
  $\displaystyle N_{\text{top}} = 1 \text{ decoder}$
**Step 2 — Sum the decoders.**
$\displaystyle \text{Total Decoders} = 32 + 8 + 2 + 1 = \boxed{42}$
</details>

---
### Q9 — Decoder with NOR Gate Circuit Expression
**Consider the circuit shown below:**
![Circuit for Q9](assets/pa4_w4pa9.png)
**The function f(x, y, z) is:**
- ( ) $\overline{x\oplus y \oplus z}$
- ( ) $M(0, 2, 4, 5, 6)$
- ( ) $\overline{z}\ \overline{y}\ \overline{x} + \overline{z}y\overline{x} + z\overline{y}\ \overline{x} + z\overline{y}x + zy\overline{x}$
- ( ) $M(1, 3, 7)$

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** $\overline{z}\ \overline{y}\ \overline{x} + \overline{z}y\overline{x} + z\overline{y}\ \overline{x} + z\overline{y}x + zy\overline{x}$, $M(1, 3, 7)$

#### ✏️ Step-by-Step Solution

**Step 1 — Analyze the decoder connections.**
The inputs to the 3-to-8 decoder are $z$ (MSB), $y$, and $x$ (LSB).
The active-high outputs of the decoder represent the minterms of the inputs:
- Wire to NOR gate from output $1 \implies m_1 = \overline{z}\ \overline{y}x$
- Wire to NOR gate from output $3 \implies m_3 = \overline{z}yx$
- Wire to NOR gate from output $7 \implies m_7 = zyx$
**Step 2 — Determine the NOR gate output expression.**
The NOR gate sums the inputs and complements the result:
$\displaystyle f = \overline{m_1 + m_3 + m_7}$
In Product of Maxterms (POS) shorthand notation:
$\displaystyle f = \boxed{M(1, 3, 7)}$
**Step 3 — Convert to SOP form.**
The minterms of $f$ are all indices except $\{1, 3, 7\}$, which are $\{0, 2, 4, 5, 6\}$:
$\displaystyle f = m_0 + m_2 + m_4 + m_5 + m_6$
$\displaystyle f = \boxed{\overline{z}\ \overline{y}\ \overline{x} + \overline{z}y\overline{x} + z\overline{y}\ \overline{x} + z\overline{y}x + zy\overline{x}}$
Thus, both highlighted options are correct representations of $f$.
</details>
