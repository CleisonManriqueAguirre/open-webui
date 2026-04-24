# Reinforced Concrete Beam Design (Flexure)

## Design Philosophy

The fundamental safety requirement:

\[
\phi \cdot C_n \ge \gamma \cdot D
\]

Where:
- \( \phi \) = strength reduction factor (capacity factor)
- \( C_n \) = nominal capacity
- \( \gamma \) = load amplification factor
- \( D \) = applied demand (moment, shear, etc.)

For flexure:

\[
\phi M_n \ge M_u
\]

---

## Section Geometry

- \( b \) = beam width (in)
- \( h \) = total height (in)
- \( d \) = effective depth (distance to tensile steel centroid)

---

## Material Properties

- Concrete compressive strength: \( f'_c \) (psi)
- Steel yield strength: \( f_y \) (psi)

Typical values:
- \( f'_c = 3000 \sim 6000 \) psi  
- \( f_y = 60,000 \) psi  

---

## Whitney Rectangular Stress Block

### Equivalent Compression Block Depth

\[
a = \beta_1 c
\]

\[
\beta_1 =
\begin{cases}
0.85 & f'_c \le 4000 \text{ psi} \\
0.85 - 0.05 \frac{f'_c - 4000}{1000} & 4000 < f'_c < 8000 \\
0.65 & f'_c \ge 8000
\end{cases}
\]

---

## Force Equilibrium

\[
T = C
\]

\[
A_s f_y = 0.85 f'_c b a
\]

Solve for \( a \):

\[
a = \frac{A_s f_y}{0.85 f'_c b}
\]

---

## Nominal Moment Capacity

\[
M_n = A_s f_y \left(d - \frac{a}{2}\right)
\]

---

## Strength Reduction Factor

Typical value for flexure:

\[
\phi = 0.9
\]

---

## Design Procedure

### 1. Compute Required Nominal Moment

\[
M_n = \frac{M_u}{\phi}
\]

---

### 2. Solve for Required Steel Area \( A_s \)

From:

\[
M_n = A_s f_y \left(d - \frac{a}{2}\right)
\]

Substitute:

\[
a = \frac{A_s f_y}{0.85 f'_c b}
\]

Solve iteratively or explicitly.

---

### 3. Minimum and Maximum Steel (Typical Constraints)

Minimum steel:

\[
A_{s,\min} = \max \left( \frac{3\sqrt{f'_c}}{f_y} b d,\; \frac{200}{f_y} b d \right)
\]

Maximum steel (to ensure ductility):

\[
A_{s,\max} \approx 0.75 A_{s,\text{balanced}}
\]

---

## Balanced Reinforcement (Reference)

\[
\rho_b = \frac{0.85 f'_c}{f_y} \cdot \frac{\beta_1}{\left( \frac{60000}{60000 + f_y} \right)}
\]

\[
A_{s,\text{balanced}} = \rho_b b d
\]

---

## Reinforcement Selection (US Bar Sizes)

| Bar | Diameter (in) | Area (in²) |
|-----|--------------|-----------|
| #3  | 3/8"         | 0.11      |
| #4  | 1/2"         | 0.20      |
| #5  | 5/8"         | 0.31      |
| #6  | 3/4"         | 0.44      |
| #7  | 7/8"         | 0.60      |
| #8  | 1"           | 0.79      |

---

## Reinforcement Requirement

\[
A_s^{provided} \ge A_s^{required}
\]

---

## Final Design Check

\[
\phi M_n \ge M_u
\]

If satisfied:
- Section is safe in flexure

---

## Notes

- Assumes singly reinforced rectangular section
- Plane sections remain plane (linear strain distribution)
- Steel yields before concrete crushing (ductile design preferred)
- Units must remain consistent (lb, in, psi)

---