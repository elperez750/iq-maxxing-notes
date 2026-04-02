


2026-04-01 20:40

Status:

Tags:

# Latex Templates

##### Author:


## References



### Notes
# LaTeX Templates

> Math rendering in Obsidian uses **MathJax/KaTeX** — wrap inline math in `$...$` and display math in `$$...$$`. Document structure commands (`\documentclass`, `\begin{document}`, etc.) don't work here — those are for Overleaf/compilers only.

---

## Quick Reference

| What you want                 | Syntax                          |
| ----------------------------- | ------------------------------- |
| Inline math                   | `$a_n = \frac{1}{2^n}$`         |
| Display math (centered block) | `$$a_n = \frac{1}{2^n}$$`       |
| Subscript                     | `$a_n$` → $a_n$                 |
| Superscript                   | `$x^2$` → $x^2$                 |
| Both                          | `$a_n^2$` → $a_n^2$             |
| Fraction                      | `$\frac{a}{b}$` → $\frac{a}{b}$ |
| Square root                   | `$\sqrt{x}$` → $\sqrt{x}$       |
| nth root                      | `$\sqrt[n]{x}$` → $\sqrt[n]{x}$ |
| Absolute value                | `$                              |
| Infinity                      | `$\infty$` → $\infty$           |
| Dots                          | `$\ldots$` → $\ldots$           |

---

## Sequences & Series

$$a_n = a(n), \quad n \in \mathbb{Z},; n \geq 0$$

$$a_n = \frac{1}{2^n} \qquad \text{(geometric, } r = \tfrac{1}{2}\text{)}$$

**Geometric sequence:** $$a_n = a_0 \cdot r^n$$

**Arithmetic sequence:** $$a_n = a_0 + nd$$

**Geometric series (converges when** $|r| < 1$**):** $$\sum_{n=0}^{\infty} a r^n = \frac{a}{1 - r}$$

**Partial sum:** $$S_n = \frac{a(1 - r^n)}{1 - r}$$

---

## Calculus

**Limit:** $$\lim_{x \to a} f(x) = L$$

**Derivative:** $$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

**Common derivatives:** $$\frac{d}{dx} x^n = nx^{n-1} \qquad \frac{d}{dx} e^x = e^x \qquad \frac{d}{dx} \ln x = \frac{1}{x}$$

**Chain rule:** $$\frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x)$$

**Definite integral:** $$\int_a^b f(x), dx = F(b) - F(a)$$

**Integration by parts:** $$\int u, dv = uv - \int v, du$$

---

## Linear Algebra

**Matrix (2×2):** $$A = \begin{pmatrix} a & b \ c & d \end{pmatrix}$$

**Determinant:** $$\det(A) = ad - bc$$

**Matrix multiplication:** $$AB = \begin{pmatrix} a & b \ c & d \end{pmatrix} \begin{pmatrix} e & f \ g & h \end{pmatrix} = \begin{pmatrix} ae+bg & af+bh \ ce+dg & cf+dh \end{pmatrix}$$

**Dot product:** $$\mathbf{u} \cdot \mathbf{v} = u_1 v_1 + u_2 v_2 + \cdots + u_n v_n$$

**Norm:** $$|\mathbf{v}| = \sqrt{v_1^2 + v_2^2 + \cdots + v_n^2}$$

**Eigenvalue equation:** $$A\mathbf{v} = \lambda \mathbf{v}$$

---

## Probability & Statistics

**Probability of A given B:** $$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$$

**Bayes' theorem:** $$P(A \mid B) = \frac{P(B \mid A), P(A)}{P(B)}$$

**Expected value:** $$E[X] = \sum_{i} x_i \cdot P(X = x_i)$$

**Variance:** $$\text{Var}(X) = E[X^2] - (E[X])^2$$

**Normal distribution PDF:** $$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$$

**Binomial coefficient:** $$\binom{n}{k} = \frac{n!}{k!(n-k)!}$$

---

## Discrete Math / CS

**Big-O:** $$T(n) = O(n \log n)$$

**Summation:** $$\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$$

**Recurrence (merge sort style):** $$T(n) = 2T!\left(\frac{n}{2}\right) + O(n)$$

**Logarithm identity:** $$\log_b x = \frac{\ln x}{\ln b}$$

**Floor / ceiling:** $$\lfloor x \rfloor \qquad \lceil x \rceil$$

**Set notation:** $$A \cup B \qquad A \cap B \qquad A \setminus B \qquad A \subseteq B$$

**Quantifiers:** $$\forall x \in \mathbb{Z}, \quad \exists n \in \mathbb{N}$$

---

## Number Sets

|Symbol|Syntax|Meaning|
|---|---|---|
|$\mathbb{N}$|`$\mathbb{N}$`|Natural numbers|
|$\mathbb{Z}$|`$\mathbb{Z}$`|Integers|
|$\mathbb{Q}$|`$\mathbb{Q}$`|Rationals|
|$\mathbb{R}$|`$\mathbb{R}$`|Reals|
|$\mathbb{C}$|`$\mathbb{C}$`|Complex numbers|

---

## Greek Letters

|Letter|Syntax|Letter|Syntax|
|---|---|---|---|
|$\alpha$|`$\alpha$`|$\Alpha$|`$\Alpha$`|
|$\beta$|`$\beta$`|$\Beta$|`$\Beta$`|
|$\gamma$|`$\gamma$`|$\Gamma$|`$\Gamma$`|
|$\delta$|`$\delta$`|$\Delta$|`$\Delta$`|
|$\epsilon$|`$\epsilon$`|$\lambda$|`$\lambda$`|
|$\theta$|`$\theta$`|$\Theta$|`$\Theta$`|
|$\mu$|`$\mu$`|$\sigma$|`$\sigma$`|
|$\pi$|`$\pi$`|$\Pi$|`$\Pi$`|
|$\phi$|`$\phi$`|$\Phi$|`$\Phi$`|
|$\omega$|`$\omega$`|$\Omega$|`$\Omega$`|

---

## Common Symbols

|Symbol|Syntax|
|---|---|
|$\leq$|`$\leq$`|
|$\geq$|`$\geq$`|
|$\neq$|`$\neq$`|
|$\approx$|`$\approx$`|
|$\equiv$|`$\equiv$`|
|$\pm$|`$\pm$`|
|$\times$|`$\times$`|
|$\cdot$|`$\cdot$`|
|$\in$|`$\in$`|
|$\notin$|`$\notin$`|
|$\subset$|`$\subset$`|
|$\rightarrow$|`$\rightarrow$`|
|$\Rightarrow$|`$\Rightarrow$`|
|$\Leftrightarrow$|`$\Leftrightarrow$`|
|$\nabla$|`$\nabla$`|
|$\partial$|`$\partial$`|

---

## Formatting Inside Math

|What|Syntax|Result|
|---|---|---|
|Bold (vectors)|`$\mathbf{v}$`|$\mathbf{v}$|
|Text inside math|`$n \text{ is even}$`|$n \text{ is even}$|
|Small space|`$a\, b$`|thin space|
|Medium space|`$a\; b$`|medium space|
|Big space|`$a \quad b$`|quad space|
|Double big space|`$a \qquad b$`|double quad|
|Overline|`$\overline{AB}$`|$\overline{AB}$|
|Underline|`$\underline{x}$`|$\underline{x}$|
|Hat|`$\hat{x}$`|$\hat{x}$|
|Bar|`$\bar{x}$`|$\bar{x}$|
|Vector arrow|`$\vec{v}$`|$\vec{v}$|

---

## Piecewise / Cases

$$f(x) = \begin{cases} x^2 & \text{if } x \geq 0 \ -x & \text{if } x < 0 \end{cases}$$

```
$$f(x) = \begin{cases} x^2 & \text{if } x \geq 0 \\ -x & \text{if } x < 0 \end{cases}$$
```

---

## Aligned Equations

$$\begin{aligned} (x+1)^2 &= x^2 + 2x + 1 \ &= x(x+2) + 1 \end{aligned}$$

```
$$\begin{aligned}
(x+1)^2 &= x^2 + 2x + 1 \\
         &= x(x+2) + 1
\end{aligned}$$
```

---

## Large Delimiters (auto-sizing)

Use `\left` and `\right` so brackets scale to the content:

$$\left( \frac{1}{2} \right) \qquad \left[ \frac{a}{b} \right] \qquad \left{ x \in \mathbb{R} \right}$$

```
$\left( \frac{1}{2} \right)$
$\left[ \frac{a}{b} \right]$
$\left\{ x \in \mathbb{R} \right\}$
```

---

## Your Image (Section 4.1.2)

The number in the $n = 4$ place for sequence $(a_n)$ is $\underline{a_4}$. We think of a sequence as a function so $\underline{a_n = a(n)}$. The number at spot $n$ where $n \in \mathbb{Z}$, $n \geq 0$ is called the **current term** $a_n$.

**Exercise 4.1.1.** Consider the sequence $\left(1, \frac{1}{2}, \frac{1}{4}, \frac{1}{8}, \frac{1}{16}, \ldots\right)$. Let $a_0 = 1$. What is $a_3$? What is $a_4$?

$$a_3 = \frac{1}{8} \qquad a_4 = \frac{1}{16}$$