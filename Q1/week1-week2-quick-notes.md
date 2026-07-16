# Week 1–2 Quick Notes

Use this as a last-minute revision sheet after reading the [full learning notes](week1-week2-learning-notes.md).

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
| $\overline A$ | NOT |
| $\overline{AB}$ | NAND |
| $\overline{A+B}$ | NOR |
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
X+\overline X=1,\quad X\overline X=0
$$

$$
X+XY=X,\quad X(X+Y)=X
$$

$$
X+\overline XY=X+Y
$$

$$
XY+X\overline Y=X
$$

$$
(X+Y)(X+\overline Y)=X
$$

$$
X(Y+Z)=XY+XZ
$$

$$
X+YZ=(X+Y)(X+Z)
$$

Consensus:

$$
XY+\overline XZ+YZ=XY+\overline XZ.
$$

## De Morgan's laws

Break the bar and change the operator:

$$
\boxed{\overline{X+Y}=\overline X\,\overline Y}
$$

$$
\boxed{\overline{XY}=\overline X+\overline Y}
$$

## Dual

To find the dual:

- swap AND and OR;
- swap 0 and 1;
- do not change variables or their complements.

Dual is not the same as complement.

## Simplification order

Why simplify: fewer gates usually means lower cost and power, less delay, and higher speed.

1. Remove $X\overline X=0$ terms.
2. Use $XX=X$.
3. Factor common literals.
4. Use $X+\overline X=1$.
5. Apply absorption/pair identities.
6. Repeat, then count gates or literals.

## SOP, POS, minterms, maxterms

| Form | Use these truth-table rows | Term rule |
|---|---|---|
| Canonical SOP / $\sum m$ | $F=1$ | bit 0 $\to$ barred; bit 1 $\to$ plain |
| Canonical POS / $\prod M$ | $F=0$ | bit 0 $\to$ plain; bit 1 $\to$ barred |

For $ABC=101$:

$$
m_5=A\overline BC
$$

$$
M_5=(\overline A+B+\overline C)
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
z+x\overline y\Rightarrow1\text{ NOT}+1\text{ AND}+1\text{ OR}=3\text{ gates}
$$

## Exam rescue routine

1. Identify the topic and write its definition/formula.
2. Check digit legality or Boolean notation.
3. Work one transformation per line.
4. Simplify before choosing an option.
5. Verify by substitution, conversion back, or a truth table.

### One source warning

`pa2.md` reports that a grader did not select the consensus identity
$xy+yz+\overline xz=xy+\overline xz$. The identity is nevertheless mathematically valid; treat this as an answer-key inconsistency.
