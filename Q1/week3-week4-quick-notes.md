# Weeks 3–4 Quick Notes

Use this for final revision after reading the [full Weeks 3–4 learning guide](week3-week4-learning-guide.md).

> **Notation:** $A'$ means NOT $A$, $AB$ means AND, and $A+B$ means OR.

## The 12 rules to remember

| Rule | Meaning |
|---|---|
| SOP $=\sum m$ | list rows where $F=1$ |
| POS $=\prod M$ | list rows where $F=0$ |
| $F=\sum m(S)$ | $F'=\prod M(S)$ |
| XOR | inputs differ; several-input XOR detects odd parity |
| XNOR | inputs match |
| probability | favorable truth-table rows divided by $2^n$ |
| NAND–NAND | natural implementation for SOP |
| NOR–NOR | natural implementation for POS |
| comparator | compare from the MSB |
| 2-to-1 MUX | $F=S'I_0+SI_1$ |
| decoder | active-high $D_i=m_i$ |
| memory chips | depth factor × width factor |

## Canonical forms

For row $ABC=101_2=5$:

$$
m_5=AB'C,
$$

$$
M_5=(A'+B+C').
$$

| Form | Rows | Bit rule |
|---|---|---|
| SOP / minterms | $F=1$ | 0 gets prime; 1 stays plain |
| POS / maxterms | $F=0$ | 0 stays plain; 1 gets prime |

For $n$ variables:

$$
\#m+\#M=2^n.
$$

Complement shortcuts:

$$
F=\sum m(S)\Rightarrow F'=\prod M(S),
$$

$$
F=\prod M(S)\Rightarrow F'=\sum m(S).
$$

## XOR, XNOR, parity, and majority

$$
A\oplus B=A'B+AB'\qquad\text{(different)}
$$

$$
A\odot B=AB+A'B'\qquad\text{(equal)}
$$

Several-input XOR is 1 for an odd number of 1s.

For binary $X=X_1X_0$, parity depends only on $X_0$. Two numbers have the same parity when:

$$
F=X_0\odot Y_0.
$$

Three-input majority:

$$
\text{at least two 1s}=AB+AC+BC.
$$

At least two 0s:

$$
A'B'+A'C'+B'C'.
$$

## Independence and probability

$F$ is independent of $X$ when:

$$
F\big|_{X=0}=F\big|_{X=1}.
$$

If simplification removes $X$, the same conclusion follows.

For independent uniform inputs:

$$
\Pr(F=1)=\frac{\#\text{1-rows}}{2^n},
$$

$$
\Pr(F=0)=\frac{\#\text{0-rows}}{2^n}.
$$

Simplify before counting.

## Reading circuits

1. Move from inputs to output.
2. Name every gate output $N_1,N_2,\ldots$.
3. A bubble means NOT.
4. Write one local equation per gate.
5. Substitute, simplify, and verify with input rows.

Switching circuits:

- series $\to$ AND;
- parallel $\to$ OR.

## NAND and NOR

NAND:

$$
X'=\text{NAND}(X,X)
$$

$$
XY=\text{NAND}(N,N),\quad N=\text{NAND}(X,Y)
$$

$$
X+Y=\text{NAND}(X',Y')
$$

NOR:

$$
X'=\text{NOR}(X,X)
$$

$$
X+Y=\text{NOR}(N,N),\quad N=\text{NOR}(X,Y)
$$

$$
XY=\text{NOR}(X',Y')
$$

Gate-count routine:

1. simplify;
2. confirm allowed fan-in;
3. check whether complemented inputs and constants are available;
4. reuse shared terms;
5. count inverters;
6. verify output polarity.

Useful direct counts:

- two-input XOR from two-input NANDs: 4;
- two-input XNOR from that XOR plus an inverter: 5.

## Delay and hazards

Add delays along one path:

$$
t_{\text{path}}=\sum t_{\text{gate}}.
$$

A glitch can occur when paths with different delays reconverge.

Introductory estimate:

$$
t_{\text{glitch}}\approx|t_{\text{arrival 1}}-t_{\text{arrival 2}}|.
$$

Analyze the paths activated by the stated input transition—not arbitrary shortest and longest paths.

Classic static-1 hazard:

$$
F=AB+A'C.
$$

Add the consensus term:

$$
F_{\text{safe}}=AB+A'C+BC.
$$

## Faults

- stuck-at-0: signal is always 0;
- stuck-at-1: signal is always 1;
- failed inverter acting as buffer: output equals input.

Compare correct and faulty final outputs for every relevant input. Count only observable changes; later logic can mask a fault.

## Comparators

One bit:

$$
A>B=AB',
$$

$$
A<B=A'B,
$$

$$
A=B=A\odot B.
$$

Two bits:

$$
A>B=A_1B_1'+(A_1\odot B_1)A_0B_0',
$$

$$
A<B=A_1'B_1+(A_1\odot B_1)A_0'B_0,
$$

$$
A=B=(A_1\odot B_1)(A_0\odot B_0).
$$

For $N=2^n$ possible values:

$$
\#(A<B)=\#(A>B)=\frac{N(N-1)}2.
$$

For two-bit numbers, this is $4\cdot3/2=6$.

## Multiplexers

Two-to-one:

$$
F=S'I_0+SI_1.
$$

Four-to-one selection:

| $S_1S_0$ | Output |
|:---:|:---:|
| 00 | $I_0$ |
| 01 | $I_1$ |
| 10 | $I_2$ |
| 11 | $I_3$ |

Implement $F(A,B,C)$ with a 4-to-1 MUX by using $A,B$ as selects:

| output pair for $C=0,1$ | connect input to |
|:---:|:---:|
| 0,0 | 0 |
| 0,1 | $C$ |
| 1,0 | $C'$ |
| 1,1 | 1 |

MUX tree:

$$
N\text{-to-1 from 2-to-1 MUXes requires }N-1.
$$

Example: $256-1=255$ MUXes.

## Decoders

An active-high $n$-to-$2^n$ decoder creates one minterm per output:

$$
D_i=m_i.
$$

- OR selected outputs $\to\sum m(\text{selected})$.
- NOR selected outputs $\to\prod M(\text{selected})$.

To address $m$ outputs, use the smallest $n$ with $2^n\ge m$.

Example:

$$
512=2^9\Rightarrow9\text{ address inputs}.
$$

For cascade counts, check enable polarity and availability of complemented inputs.

## Encoders

A normal encoder assumes one active input. A priority encoder permits several active inputs and reports the highest-priority one.

Decimal-to-BCD equations:

$$
A_0=D_1+D_3+D_5+D_7+D_9,
$$

$$
A_1=D_2+D_3+D_6+D_7,
$$

$$
A_2=D_4+D_5+D_6+D_7,
$$

$$
A_3=D_8+D_9.
$$

With at most five inputs per OR gate: 4 gates.

## Memory expansion

$$
\text{depth factor}=\frac{\text{target words}}{\text{chip words}}
$$

$$
\text{width factor}=\frac{\text{target bits/word}}{\text{chip bits/word}}
$$

$$
\text{chips}=\text{depth factor}\times\text{width factor}.
$$

Address bits depend on word count:

$$
\text{address bits}=\log_2(\text{number of words}).
$$

For 64K × 32 from 2K × 8:

- depth factor $=32$;
- width factor $=4$;
- chips $=128$;
- target address bits $=16$;
- chip address bits $=11$;
- bank-select bits $=5$.

## Final exam checklist

1. Fix the variable order and identify the row indices.
2. Translate the sentence or diagram into a function.
3. Simplify before counting hardware.
4. Check bubbles, active level, and select-line ordering.
5. Match the requested form: SOP, POS, gate count, probability, or block count.
6. Verify with a truth table or carefully chosen input cases.

For explanations and worked examples, return to the [full learning guide](week3-week4-learning-guide.md).
