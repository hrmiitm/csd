# Week 1–2 Quick Notes

Use this as a last-minute revision sheet after reading the [full learning notes](week1-week2-learning-notes.md).

> **Read these first:** bit formulas, base rules, De Morgan's laws, and the SOP/POS table. Together they solve most Week 1–2 questions.

> **NOT notation:** $A'$ means “NOT A.” It is the same as the line-above-a-letter notation used in some assignment questions.

## The 6 must-remember rules

| Rule | Meaning |
|---|---|
| $2^n$ | number of patterns from $n$ bits |
| $2^n-1$ | largest unsigned $n$-bit value |
| digit $<b$ | a digit must be smaller than its base |
| base conversion | use place values, then repeated division |
| De Morgan | move NOT inside and swap AND/OR |
| SOP/POS | SOP uses 1-rows; POS uses 0-rows |

## Bits

$$
\boxed{n\text{ bits give }2^n\text{ patterns}}
$$

$$
\boxed{\text{largest unsigned }n\text{-bit value}=2^n-1}
$$

$$
\boxed{\text{bits for }N=\lfloor\log_2N\rfloor+1\quad(N\ge1)}
$$

Power-of-2 trap: $32=2^5=(100000)_2$, so it needs 6 bits.

## Number bases

- In base $b$, every digit must be $<b$.
- Positional value: $(d_nd_{n-1}\ldots d_0)_b=\sum d_i b^i$.
- Fractional positions use $b^{-1},b^{-2},\ldots$.
- Base $a$ to base $b$: base $a\rightarrow$ decimal $\rightarrow$ base $b$.
- Decimal to another base: repeated division; read remainders bottom to top.
- Unknown base: expand into a polynomial, solve, check digit legality, substitute back.
- Hex digits: $A=10,B=11,C=12,D=13,E=14,F=15$.

## Moore's law

Course model: transistor count doubles every 2 years.

$$
\boxed{T=T_0\,2^{y/2}}
$$

## Voltage logic

$$
V\le V_L\Rightarrow0,\qquad V\ge V_H\Rightarrow1
$$

$$
V_L<V<V_H\Rightarrow\text{illegal/undefined}
$$

## Computer-system facts

- Highest transformation abstraction: **computational problem**.
- Transformation path: problem $\to$ algorithm $\to$ language $\to$ system software $\to$ architecture $\to$ microarchitecture $\to$ hardware.
- PCBs contain ICs.
- Modules contain cells; cells contain gates; transistor circuits implement gates.
- The usual physical encoding of bits is voltage.
- A good bit is small/cheap, stable/reliable, and fast/easy to manipulate.

## Gate meanings

| Expression | Gate |
|---|---|
| $A+B$ | OR |
| $AB$ | AND |
| $A'$ | NOT |
| $(AB)'$ | NAND |
| $(A+B)'$ | NOR |
| $A\oplus B$ | XOR: inputs differ |
| $A\odot B$ | XNOR: inputs match |

## Boolean laws

$$
X+0=X,\quad X1=X,\quad X+1=1,\quad X0=0
$$

$$
X+X=X,\quad XX=X
$$

$$
X+X'=1,\quad XX'=0
$$

$$
X+XY=X,\quad X(X+Y)=X
$$

$$
X+X'Y=X+Y
$$

$$
XY+XY'=X
$$

$$
(X+Y)(X+Y')=X
$$

$$
X(Y+Z)=XY+XZ
$$

$$
X+YZ=(X+Y)(X+Z)
$$

Consensus:

$$
XY+X'Z+YZ=XY+X'Z.
$$

## De Morgan's laws

Move NOT inside and change the operator:

$$
(X+Y)'=X'\,Y'
$$

$$
(XY)'=X'+Y'
$$

## Dual

To find the dual:

- swap AND and OR;
- swap 0 and 1;
- do not change variables or their complements.

Dual is not the same as complement.

## Simplification order

Why simplify: fewer gates usually means lower cost and power, less delay, and higher speed.

1. Remove $XX'=0$ terms.
2. Use $XX=X$.
3. Factor common literals.
4. Use $X+X'=1$.
5. Apply absorption/pair identities.
6. Repeat, then count gates or literals.

## SOP, POS, minterms, maxterms

| Form | Use these truth-table rows | Term rule |
|---|---|---|
| Canonical SOP / $\sum m$ | $F=1$ | bit 0 $\to$ NOT; bit 1 $\to$ plain |
| Canonical POS / $\prod M$ | $F=0$ | bit 0 $\to$ plain; bit 1 $\to$ NOT |

For $ABC=101$:

$$
m_5=AB'C
$$

$$
M_5=(A'+B+C')
$$

Memory line:

$$
\boxed{\text{SOP finds the 1s; POS finds the 0s}}
$$

With $n$ variables, a truth table has $2^n$ rows.

## Gate-count checklist

- Simplify first.
- Check whether complemented inputs are already available.
- Count each required NOT, AND, and OR gate.
- Respect “2-input gate” restrictions.
- Reuse a shared intermediate result instead of counting it twice.

Examples:

$$
AC+ABC=AC\Rightarrow1\text{ AND gate}
$$

$$
z+xy'\Rightarrow1\text{ NOT}+1\text{ AND}+1\text{ OR}=3\text{ gates}
$$

## Exam rescue routine

1. Identify the topic and write its definition/formula.
2. Check digit legality or Boolean notation.
3. Work one transformation per line.
4. Simplify before choosing an option.
5. Verify by substitution, conversion back, or a truth table.

### One source warning

`pa2.md` reports that a grader did not select the consensus identity
$xy+yz+x'z=xy+x'z$. The identity is nevertheless mathematically valid; treat this as an answer-key inconsistency.
