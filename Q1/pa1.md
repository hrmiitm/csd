# Week 1 — Practice Assignment 1
---

### Q1 — Distinct Characters in 6-bit Binary Code
**A computer system uses a 6-bit binary code to represent characters. How many distinct characters can this system represent?**
- ( ) 63
- ( ) 64
- ( ) 32
- ( ) 12

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** 64

#### ✏️ Step-by-Step Solution

**Step 1 — Understand binary representation capacity.**
Each bit in a binary code can represent one of 2 states: $0$ or $1$. For a code with $n$ bits, the total number of unique binary combinations (or distinct representations) is given by:
$$
\text{Total Combinations} = 2^n
$$
**Step 2 — Calculate for 6 bits.**
Given $n = 6$:
$$
2^6 = 2 \times 2 \times 2 \times 2 \times 2 \times 2 = \boxed{64}
$$
Thus, the system can represent up to 64 distinct characters.
</details>

---
### Q2 — Largest Binary Number Expressible with 10 Bits
**What is the largest binary number that can be expressed with 10 bits?**
- ( ) $(1777)_8$
- ( ) $(1777)_9$
- ( ) $(999)_{10}$
- ( ) $(3FF)_{16}$

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** $(1777)_8$, $(3FF)_{16}$

#### ✏️ Step-by-Step Solution

**Step 1 — Determine the maximum decimal value.**
The largest binary number represented by $n$ bits has all bits set to $1$. In decimal, this maximum value is:
$$
\text{Max Value} = 2^n - 1
$$
For $n = 10$:
$$
2^{10} - 1 = 1024 - 1 = 1023
$$
So we need to find which options are equivalent to the decimal value $1023$.
**Step 2 — Convert 1023 to octal (base 8).**
Perform successive division by 8:
$$
\begin{aligned}
1023 \div 8 &= 127 \quad \text{remainder } 7 \\
127 \div 8 &= 15 \quad \text{remainder } 7 \\
15 \div 8 &= 1 \quad \text{remainder } 7 \\
1 \div 8 &= 0 \quad \text{remainder } 1
\end{aligned}
$$
Reading the remainders from bottom to top gives $(1777)_8$. Thus, this option is **correct**.
**Step 3 — Convert 1023 to hexadecimal (base 16).**
Perform successive division by 16:
$$
\begin{aligned}
1023 \div 16 &= 63 \quad \text{remainder } 15 \ (F) \\
63 \div 16 &= 3 \quad \text{remainder } 15 \ (F) \\
3 \div 16 &= 0 \quad \text{remainder } 3
\end{aligned}
$$
Reading the remainders from bottom to top gives $(3FF)_{16}$. Thus, this option is **correct**.
**Step 4 — Verify other options.**
- $(1777)_9 = 1 \times 9^3 + 7 \times 9^2 + 7 \times 9 + 7 = 729 + 567 + 63 + 7 = 1366 \neq 1023$
- $(999)_{10} = 999 \neq 1023$
Therefore, the correct representations are $(1777)_8$ and $(3FF)_{16}$.
</details>

---
### Q3 — Primary Information Encoding in Computers
**What is the primary choice for encoding information in computer systems?**
- ( ) Current
- ( ) Phase
- ( ) Voltage
- ( ) Frequency

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** Voltage

#### ✏️ Step-by-Step Solution

**Step 1 — Understand physical representations of logic values.**
In modern electronic computing systems, digital information (binary 0 and 1) must be mapped to physical quantities. The options are electric current, signal phase, voltage levels, or frequency.
**Step 2 — Identify the industry standard choice.**
Voltage is the standard choice in CMOS technology because:
1. It is easy to generate and measure using semiconductor switches (transistors).
2. It allows systems to consume negligible static power when states are not switching.
3. High voltage levels can represent logic 1, and low voltage levels (ground) can represent logic 0.
Thus, **Voltage** is the primary choice.
</details>

---
### Q4 — Importance of Hardware and Software Understanding
**Why is it important to understand both hardware and software in computer systems?**
- ( ) To develop better software
- ( ) To design better hardware
- ( ) To design a better computing system
- ( ) All of the above

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** All of the above

#### ✏️ Step-by-Step Solution

**Step 1 — Recognize the co-design nature of computer systems.**
Modern computer engineering relies on hardware-software co-design. Software runs on hardware, and hardware is built to execute software efficiently.
**Step 2 — Evaluate the options.**
- **Software Developers**: Benefit from knowing hardware limitations (e.g., cache sizes, pipelining) to write high-performance programs.
- **Hardware Designers**: Benefit from knowing the demands of compilers and operating systems to optimize instruction set architectures (ISAs).
- **System Architects**: Must understand both to balance trade-offs and build well-optimized, cost-effective computing systems.
Thus, "All of the above" is the correct choice.
</details>

---
### Q5 — Characteristics of a Good Representation Bit
**What makes a good bit for representing information?**
- ( ) Small and inexpensive
- ( ) Stable and reliable
- ( ) Easy and fast to manipulate
- ( ) All of the above

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** All of the above

#### ✏️ Step-by-Step Solution

**Step 1 — Analyze the physical requirements of computer memory and processing elements.**
A "bit" in memory must represent a binary state reliably over billions of cycles while fitting inside microscopic areas.
**Step 2 — Check each criterion.**
- **Small and inexpensive**: Essential for packing billions of transistors onto a single silicon die (high density and low cost).
- **Stable and reliable**: The state must not flip due to minor thermal noise or electromagnetic interference.
- **Easy and fast to manipulate**: We must be able to write and read states at gigahertz speeds.
Thus, all these characteristics are critical.
</details>

---
### Q6 — Module Composition in Computing Hierarchy
**In Complex Computer Systems, Modules are composed of:**
- ( ) ICs
- ( ) PCBs
- ( ) Transistors
- ( ) Cells

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** Cells

#### ✏️ Step-by-Step Solution

**Step 1 — Recall the abstraction level hierarchy.**
In digital system design, complexity is managed using hierarchical levels of abstraction (from top to bottom):
$$
\text{System} \rightarrow \text{Board (PCB)} \rightarrow \text{Modules} \rightarrow \text{Cells (Standard Cells)} \rightarrow \text{Gates} \rightarrow \text{Circuits} \rightarrow \text{Devices (Transistors)}
$$
**Step 2 — Locate the direct component level below modules.**
Modules (such as ALU, multiplexers, and adders) are built by connecting standard functional blocks called **Cells** (e.g., flip-flops, half-adders).
Therefore, modules are directly composed of **Cells**.
</details>

---
### Q7 — Moore's Law Transistor Scaling
**According to Moore’s Law, how does the number of transistors in a dense integrated circuit change every two years?**
- ( ) Doubles
- ( ) Triples
- ( ) Quadruples
- ( ) Quintuples

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** Doubles

#### ✏️ Step-by-Step Solution

**Step 1 — Recall the formulation of Moore's Law.**
Moore's Law is an empirical observation made by Intel co-founder Gordon Moore in 1965.
**Step 2 — Identify the rate of scaling.**
He observed that the number of transistors on a microchip **doubles** approximately every two years, which has historically driven exponential advances in computing power and reductions in cost.
</details>

---
### Q8 — Decimal to Binary Conversion: 647
**Convert $(647)_{10}$ to binary**

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{1010000111}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Perform successive division by 2.**
Divide 647 by 2 repeatedly and track the remainders:
$$
\begin{aligned}
647 \div 2 &= 323 \quad \text{remainder } 1 \\
323 \div 2 &= 161 \quad \text{remainder } 1 \\
161 \div 2 &= 80 \quad \text{remainder } 1 \\
80 \div 2 &= 40 \quad \text{remainder } 0 \\
40 \div 2 &= 20 \quad \text{remainder } 0 \\
20 \div 2 &= 10 \quad \text{remainder } 0 \\
10 \div 2 &= 5 \quad \text{remainder } 0 \\
5 \div 2 &= 2 \quad \text{remainder } 1 \\
2 \div 2 &= 1 \quad \text{remainder } 0 \\
1 \div 2 &= 0 \quad \text{remainder } 1
\end{aligned}
$$
**Step 2 — Assemble the binary representation.**
Read the remainders from bottom to top:
$$
(647)_{10} = \boxed{(1010000111)_2}
$$
</details>

---
### Q9 — Structural Hierarchy in Computer Systems
**Select the correct option(s):**
- ( ) PCBs are made up of ICs
- ( ) Modules are made up of ICs
- ( ) Gates are made up of Cells
- ( ) Modules are made up of Cells

<details>
<summary><b>Answer & Solution</b></summary>

**Answer:** PCBs are made up of ICs, Modules are made up of Cells

#### ✏️ Step-by-Step Solution

**Step 1 — Examine physical board-level structure.**
A Printed Circuit Board (PCB) is a physical board on which Integrated Circuits (ICs), resistors, capacitors, and connectors are soldered. Therefore, **PCBs are made up of ICs** is correct.
**Step 2 — Examine digital design abstraction hierarchy.**
In logical system abstraction:
- **Modules** (e.g., ALU) are composed of standard **Cells**.
- **Cells** (e.g., full adders) are composed of basic logic **Gates** (AND, OR, NOT).
- **Gates** are implemented using electrical **Circuits** containing transistors.
Thus, **Modules are made up of Cells** is correct.
</details>

---
### Q10 — Find Base for Equation 514/20 = 24.2
**What will be the base of the number system such that the following equation holds?**
$$
\frac{514}{20} = 24.2
$$

<details>
<summary><b>Answer & Solution</b></summary>

**Answer: $\boxed{7}$**

#### ✏️ Step-by-Step Solution

**Step 1 — Write the positional representation in base $b$.**
Let $b$ be the base of the number system. We can convert each term to base 10 polynomial form:
- $514_b = 5b^2 + 1b^1 + 4b^0 = 5b^2 + b + 4$
- $20_b = 2b^1 + 0b^0 = 2b$
- $24.2_b = 2b^1 + 4b^0 + 2b^{-1} = 2b + 4 + \frac{2}{b}$
**Step 2 — Set up the equation and solve for $b$.**
$$
\frac{5b^2 + b + 4}{2b} = 2b + 4 + \frac{2}{b}
$$
Multiply the entire equation by $2b$ to clear the denominators (noting that base $b \geq 6$ since the digit $5$ is used):
$$
5b^2 + b + 4 = 2b \left(2b + 4 + \frac{2}{b}\right)
$$
$$
5b^2 + b + 4 = 4b^2 + 8b + 4
$$
Subtract $4b^2 + 8b + 4$ from both sides:
$$
b^2 - 7b = 0
$$
$$
b(b - 7) = 0
$$
**Step 3 — Choose the valid base.**
The roots are $b = 0$ or $b = 7$.
Since a base must be greater than the largest digit present in the numbers ($5$ in $514_b$), the base must be $b \geq 6$.
Thus, $b = \boxed{7}$.
</details>
