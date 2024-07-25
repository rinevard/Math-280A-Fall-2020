# Homework 2

## Problem 1
Let $\Omega = \{1, 2, 3, 4\}$, and set $S = \{\emptyset, \{1\}, \{2\}, \{3, 4\}, \Omega\}$.

(a) Prove that $S$ is a semi-algebra. \
(b) Define $\chi: S \to \mathbb{R}$ as follows:

$$\chi(\emptyset) = 0, \chi(\{1\}) = \chi(\{2\}) = \chi(\{3, 4\}) = 1, \chi(\Omega) = 4.$$

Show that $\chi$ is "pairwise" additive: $\chi(A \cup B) = \chi(A) + \chi(B)$ whenever $A, B,$ and $A \cup B$ are all in $S$. Show also that $\chi$ is not additive over all finite disjoint unions.

(This shows it is important, when dealing with semi-algebras and other classes not closed under finite union, to spell out the full statement of "finite additivity" in all proofs.)

## Solution

### (a) $S$ is a semi-algebra.

1. **Non-empty and Contains $\Omega$:**

   Clearly, $\Omega \in S$ and $\emptyset \in S$.

2. **Closed under Intersection:**

   We need to check that the intersection of any two sets in $S$ is also in $S$:
   - $\emptyset \cap A = \emptyset$ for any $A \in S$.
   - $\{1\} \cap \{2\} = \emptyset$.
   - $\{1\} \cap \{3, 4\} = \emptyset$.
   - $\{2\} \cap \{3, 4\} = \emptyset$.
   - $\{3, 4\} \cap \Omega = \{3, 4\}$.
   - $\{1\} \cap \Omega = \{1\}$.
   - $\{2\} \cap \Omega = \{2\}$.
   - $\Omega \cap \Omega = \Omega$.

   All these intersections are in $S$, so $S$ is closed under intersections.

3. **Complement Property:**

   We need to check that the complement of any set in $S$ can be written as a finite disjoint union of sets in $S$:
   - $\emptyset^c = \Omega$.
   - $\{1\}^c = \{2, 3, 4\} = \{2\} \cup \{3, 4\}$
   - $\{2\}^c = \{1, 3, 4\} = \{1\} \cup \{3, 4\}$
   - $\{3, 4\}^c = \{1, 2\} = \{1\} \cup \{2\}$
   - $\Omega^c = \emptyset$.

   Thus, $S$ satisfies the complement condition.

Since $S$ is closed under intersections and complements can be expressed as finite disjoint unions of sets in $S$, $S$ is a semi-algebra.

### (b) $\chi$ is "pairwise" additive but not additive over all finite disjoint unions.

1. **Pairwise Additivity:**

   We need to show that $\chi(A \cup B) = \chi(A) + \chi(B)$ whenever $A, B,$ and $A \cup B$ are all in $S$:
   - $\chi(\emptyset \cup A) = \chi(A) = \chi(\emptyset) + \chi(A)$ for any $A \in S$.
   - $\chi(\{1\} \cup \{2\}) = \chi(\{1, 2\}) = 2 = \chi(\{1\}) + \chi(\{2\})$.
   - $\chi(\{1\} \cup \{3, 4\}) = \chi(\{1, 3, 4\}) = 2 = \chi(\{1\}) + \chi(\{3, 4\})$.
   - $\chi(\{2\} \cup \{3, 4\}) = \chi(\{2, 3, 4\}) = 2 = \chi(\{2\}) + \chi(\{3, 4\})$.
   - $\chi(\{1\} \cup \Omega) = \chi(\Omega) = 4 = \chi(\{1\}) + \chi(\Omega)$.

   In all cases, pairwise additivity holds.

2. **Non-Additivity over All Finite Disjoint Unions:**

   Consider the sets $\{1\}$, $\{2\}$, and $\{3, 4\}$ which are disjoint and their union is $\Omega$:
   $$
   \chi(\{1\} \cup \{2\} \cup \{3, 4\}) = \chi(\Omega) = 4
   $$
   but
   $$
   \chi(\{1\}) + \chi(\{2\}) + \chi(\{3, 4\}) = 1 + 1 + 1 = 3.
   $$

   Thus, $\chi$ is not additive over all finite disjoint unions.

Therefore, $\chi$ is pairwise additive but not additive over all finite disjoint unions. $\blacksquare$



---
## Problem 2
(Exercise 4.12 in Driver) Let $\Omega_1$ and $\Omega_2$ be sets, and let $\mathcal{A}_1 \subseteq 2^{\Omega_1}$ and $\mathcal{A}_2 \subseteq 2^{\Omega_2}$ be semi-algebras. Show that

$$S = \mathcal{A}_1 \times \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\} \subseteq 2^{\Omega_1 \times \Omega_2}$$

is a semi-algebra.

## Solution

To prove that $S$ is a semi-algebra, we need to show the following properties:

### 1. Empty Set and Whole Set:

Since $\mathcal{A}_1$ and $\mathcal{A}_2$ are semi-algebras, they both contain the empty set $\emptyset$ and their respective whole sets $\Omega_1$ and $\Omega_2$. Therefore, 

$$
\emptyset \times \emptyset = \emptyset \in S,
$$

and

$$
\Omega_1 \times \Omega_2 \in S.
$$

Thus, $\emptyset \in S$ and $\Omega_1 \times \Omega_2 \in S$.

### 2. Closed under Intersection:

Let $X_1 = A_1 \times A_2$ and $X_2 = B_1 \times B_2$ where $A_1, B_1 \in \mathcal{A}_1$ and $A_2, B_2 \in \mathcal{A}_2$. Then,

$$
\begin{align*}
X_1 \cap X_2 &= (A_1 \times A_2) \cap (B_1 \times B_2) \\
&= (A_1 \cap B_1) \times (A_2 \cap B_2)
\end{align*}
$$

Since $\mathcal{A}_1$ and $\mathcal{A}_2$ are semi-algebras, $A_1 \cap B_1 \in \mathcal{A}_1$ and $A_2 \cap B_2 \in \mathcal{A}_2$. Thus,

$$
(A_1 \cap B_1) \times (A_2 \cap B_2) \in S.
$$

Hence, $S$ is closed under intersection.

### 3. Complementation Property:

Let $X = A_1 \times A_2$ where $A_1 \in \mathcal{A}_1$ and $A_2 \in \mathcal{A}_2$. We need to show that $X^c$ can be expressed as a finite union of disjoint sets in $S$. 

We decompose $X^c$ into a union of three parts:

$$
X^c = (A_1^c \times A_2) \cup (A_1 \times A_2^c) \cup (A_1^c \times A_2^c).
$$

To show that LHS = RHS:

$$
\begin{align*}
X^c &= (A_1 \times A_2)^c \\
&= \{(x,y) : (x,y) \notin A_1 \times A_2\} \\
&= \{(x,y) : x \notin A_1 \text{ or } y \notin A_2\} \\
&= \{(x,y) : x \in A_1^c \text{ and } y \in A_2\} \cup \{(x,y) : x \in A_1 \text{ and } y \in A_2^c\} \cup \{(x,y) : x \in A_1^c \text{ and } y \in A_2^c\} \\
&= (A_1^c \times A_2) \cup (A_1 \times A_2^c) \cup (A_1^c \times A_2^c)
\end{align*}
$$

To show that these three parts are disjoint, observe that:

$$
\begin{align*}
& (A_1^c \times A_2) \cap (A_1 \times A_2^c) 
\\
= &(A_1^c \cap A_1) \times (A_2 \cap A_2^c)
= \emptyset
\\
& (A_1^c \times A_2) \cap (A_1^c \times A_2^c)
\\
= &(A_1^c \cap A_1^c) \times (A_2 \cap A_2^c)
= \emptyset
\\
& (A_1 \times A_2^c) \cap (A_1^c \times A_2^c)
\\
= &(A_1 \cap A_1^c) \times (A_2^c \cap A_2^c)
= \emptyset
\end{align*}
$$

Since $\mathcal{A}_1$ and $\mathcal{A}_2$ are semi-algebras, $A_1^c \in \mathcal{A}_1$ and $A_2^c \in \mathcal{A}_2$. Therefore,

$$
(A_1^c \times A_2) \in S, \quad (A_1 \times A_2^c) \in S, \quad (A_1^c \times A_2^c) \in S.
$$

Thus, $X^c$ can be expressed as a finite union of disjoint sets in $S$.


Since $S$ satisfies all three properties of a semi-algebra, we conclude that $S$ is indeed a semi-algebra. $\blacksquare$



---
## Problem 3
(Exercise 4.3 in Driver) Let $A_n, B_n \subseteq \Omega$ for $n \in \mathbb{N}$. Show that

$$\left(\bigcup_{n=1}^{\infty} A_n\right) \setminus \left(\bigcup_{n=1}^{\infty} B_n\right) \subseteq \bigcup_{n=1}^{\infty}(A_n \setminus B_n).$$

Use this to show that

$$\left(\bigcup_{n=1}^{\infty} A_n\right) \triangle \left(\bigcup_{n=1}^{\infty} B_n\right) \subseteq \bigcup_{n=1}^{\infty}(A_n \triangle B_n).$$

## Solution

Let $A_n, B_n \subseteq \Omega$ for $n \in \mathbb{N}$. We will prove the following two statements:

### 1. $\left(\bigcup_{n=1}^{\infty} A_n\right) \setminus \left(\bigcup_{n=1}^{\infty} B_n\right) \subseteq \bigcup_{n=1}^{\infty}(A_n \setminus B_n)$

**Proof:**

Let $x \in \left(\bigcup_{n=1}^{\infty} A_n\right) \setminus \left(\bigcup_{n=1}^{\infty} B_n\right)$. This means:

1. $x \in \bigcup_{n=1}^{\infty} A_n$
2. $x \notin \bigcup_{n=1}^{\infty} B_n$

From (1), $\exists k \in \mathbb{N}$ such that $x \in A_k$.
From (2), $\forall n \in \mathbb{N}, x \notin B_n$. In particular, $x \notin B_k$.

Therefore, $x \in A_k \setminus B_k \subseteq \bigcup_{n=1}^{\infty}(A_n \setminus B_n)$.

Thus, we have
$$\left(\bigcup_{n=1}^{\infty} A_n\right) \setminus \left(\bigcup_{n=1}^{\infty} B_n\right) \subseteq \bigcup_{n=1}^{\infty}(A_n \setminus B_n)$$

### 2. $\left(\bigcup_{n=1}^{\infty} A_n\right) \triangle \left(\bigcup_{n=1}^{\infty} B_n\right) \subseteq \bigcup_{n=1}^{\infty}(A_n \triangle B_n)$

**Proof:**

Recall that for any sets $X$ and $Y$, $X \triangle Y = (X \setminus Y) \cup (Y \setminus X)$.

Let $L = \left(\bigcup_{n=1}^{\infty} A_n\right) \triangle \left(\bigcup_{n=1}^{\infty} B_n\right)$ and $R = \bigcup_{n=1}^{\infty}(A_n \triangle B_n)$.

$$\begin{align*}
L &= \left( \left(\bigcup_{n=1}^{\infty} A_n\right) \setminus \left(\bigcup_{n=1}^{\infty} B_n\right)\right ) \cup \left( \left(\bigcup_{n=1}^{\infty} B_n\right) \setminus \left(\bigcup_{n=1}^{\infty} A_n\right)\right ) \\
&\subseteq \bigcup_{n=1}^{\infty}(A_n \setminus B_n) \cup \bigcup_{n=1}^{\infty}(B_n \setminus A_n) \quad \text{(by part 1)} \\
&= \bigcup_{n=1}^{\infty}((A_n \setminus B_n) \cup (B_n \setminus A_n)) \\
&= \bigcup_{n=1}^{\infty}(A_n \triangle B_n) = R
\end{align*}$$

Thus, we have shown that $L \subseteq R$, which completes the proof. $\blacksquare$


---
## Problem 4
(Exercise 4.4 in Driver) Let $A, B, C \subseteq \Omega$. Recall that the **symmetric difference** of sets is $A \triangle B = (A \cap B^c) \cup (B \cap A^c)$.

(a) Show that $A \cap C^c \subseteq (A \cap B^c) \cup (B \cap C^c)$.

(b) Use part (a) to show that

$$A \triangle C \subseteq (A \triangle B) \cup (B \triangle C).$$

(c) Now, let $\nu: 2^\Omega \to [0, \infty)$ be an outer measure. Show that the function $d: 2^\Omega \times 2^\Omega \to [0, \infty)$ defined by $d(A, B) = \nu(A \triangle B)$ satisfies the **triangle inequality**:

$$d(A, C) \leq d(A, B) + d(B, C).$$




---
## Problem 5
Let $\mathcal{A}$ be a field over $\Omega$, and let $\mathbb{P}$ be a probability measure on $(\Omega, \sigma(\mathcal{A}))$. Let $B \in \sigma(\mathcal{A})$. Prove that for any $\epsilon > 0$, there is a set $A \in \mathcal{A}$ such that $\mathbb{P}(A \triangle B) < \epsilon$. I.e. $\mathcal{A}$ is "dense" in $\sigma(\mathcal{A})$. \
[Hint: show that the collection of all sets $B$ satisfying this property is a $\sigma$-field.]