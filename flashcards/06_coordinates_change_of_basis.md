+++
order = 6
tags = ["math", "linear-algebra", "coordinates", "change-of-basis", "isomorphism"]
+++

# Linear Algebra — Coordinates and Change of Basis

## 6.1 Why Coordinates

Q: Why do we bother introducing coordinate vectors instead of working with vectors directly?
A: Coordinates let us represent any vector in an $n$-dimensional space as an ordered tuple in $\mathbb{R}^n$, which is computable with familiar tools (row reduction, matrix multiplication). They turn abstract spaces like polynomials or matrices into concrete column vectors we can manipulate numerically.

Q: Why does the choice of basis matter when assigning coordinates?
A: The same vector $\vec{x}$ has different coordinate tuples depending on which basis we measure against, because each basis provides a different "ruler." Picking a basis is like picking a coordinate system on a plane: the point is fixed, but the numbers describing it change.

Q: Before seeing the definition, predict: if $\mathcal{B} = \{\vec{b}_1, \vec{b}_2\}$ is a basis of $V$ and $\vec{x} = 3\vec{b}_1 - 2\vec{b}_2$, what should $[\vec{x}]_\mathcal{B}$ be?
A: The coordinate vector should be $(3, -2)$ — the tuple of scalars that rebuilds $\vec{x}$ from the basis vectors.

## 6.2 Coordinate Vector Definition

C: Given an ordered basis $\mathcal{B} = \{\vec{b}_1, \ldots, \vec{b}_n\}$ of $V$, the [coordinate vector] of $\vec{x}$ relative to $\mathcal{B}$, written $[\vec{x}]_\mathcal{B}$, is the tuple $(c_1, \ldots, c_n)$ of scalars such that $\vec{x} = c_1\vec{b}_1 + \cdots + c_n\vec{b}_n$.

Q: Why is the coordinate vector $[\vec{x}]_\mathcal{B}$ uniquely determined?
A: Because $\mathcal{B}$ is a basis, it is linearly independent, so the only way to write $\vec{x}$ as a linear combination of the $\vec{b}_i$'s is with one specific set of scalars. If two expansions existed, subtracting them would give a nontrivial dependence among the $\vec{b}_i$, contradicting independence.

C: Uniqueness of coordinates comes from the [linear independence] of the basis vectors.

Q: Why must the basis $\mathcal{B}$ be ordered when writing $[\vec{x}]_\mathcal{B}$?
A: A coordinate vector is a tuple, so the position of each scalar matters. Permuting the basis vectors permutes the coordinates, giving a different element of $\mathbb{R}^n$ even though it represents the same $\vec{x}$.

C: The coordinate vector $[\vec{x}]_\mathcal{B}$ lives in $[\mathbb{R}^n]$, where $n = \dim V$.

## 6.3 The Change-of-Coordinates Map

C: The map $\vec{x} \mapsto [\vec{x}]_\mathcal{B}$ from $V$ to $\mathbb{R}^n$ is called the [change-of-coordinates map].

Q: Why is the change-of-coordinates map linear?
A: If $\vec{x} = \sum c_i\vec{b}_i$ and $\vec{y} = \sum d_i\vec{b}_i$, then $\vec{x} + \vec{y} = \sum(c_i + d_i)\vec{b}_i$ and $\alpha\vec{x} = \sum(\alpha c_i)\vec{b}_i$. So coordinates of sums are sums of coordinates, and coordinates of scalar multiples are scalar multiples of coordinates.

Q: Why is the change-of-coordinates map invertible?
A: Every tuple $(c_1, \ldots, c_n) \in \mathbb{R}^n$ corresponds to exactly one vector $\sum c_i\vec{b}_i \in V$, so the map is a bijection. This bijection plus linearity means it is an isomorphism.

C: The change-of-coordinates map $\vec{x} \mapsto [\vec{x}]_\mathcal{B}$ is both [linear] and [invertible].

## 6.4 The Change-of-Basis Matrix

C: Given a basis $\mathcal{B} = \{\vec{b}_1, \ldots, \vec{b}_n\}$ of $\mathbb{R}^n$, the [change-of-basis matrix] $P_\mathcal{B}$ has the basis vectors $\vec{b}_1, \ldots, \vec{b}_n$ as its columns.

Q: Why are the basis vectors placed as the columns of $P_\mathcal{B}$ rather than the rows?
A: If $[\vec{x}]_\mathcal{B} = (c_1, \ldots, c_n)$, then $\vec{x} = c_1\vec{b}_1 + \cdots + c_n\vec{b}_n$. This linear combination is exactly the matrix-vector product $P_\mathcal{B}[\vec{x}]_\mathcal{B}$ when the $\vec{b}_i$ are the columns, because each $c_i$ scales a column.

C: The defining identity of the change-of-basis matrix is $\vec{x} = [P_\mathcal{B}[\vec{x}]_\mathcal{B}]$.

Q: Why is $P_\mathcal{B}$ always invertible?
A: Its columns are the vectors of a basis, so they are linearly independent and span $\mathbb{R}^n$. By the invertible matrix theorem, a square matrix with linearly independent columns is invertible.

C: The columns of $P_\mathcal{B}$ are [linearly independent], which is why $P_\mathcal{B}$ is invertible.

## 6.5 Converting to $\mathcal{B}$-Coordinates

Q: Given $\vec{x} \in \mathbb{R}^n$ and a basis $\mathcal{B}$, how do you compute $[\vec{x}]_\mathcal{B}$?
A: Solve the linear system $P_\mathcal{B}[\vec{x}]_\mathcal{B} = \vec{x}$ for the unknown coordinate vector, where $P_\mathcal{B}$ has the basis vectors as columns. Equivalently, $[\vec{x}]_\mathcal{B} = P_\mathcal{B}^{-1}\vec{x}$.

C: Solving for $\mathcal{B}$-coordinates explicitly: $[\vec{x}]_\mathcal{B} = [P_\mathcal{B}^{-1}\vec{x}]$.

Q: Why is computing $[\vec{x}]_\mathcal{B}$ just a linear system solve in disguise?
A: Finding coordinates means finding scalars $c_i$ with $c_1\vec{b}_1 + \cdots + c_n\vec{b}_n = \vec{x}$. Stacking the $\vec{b}_i$ as columns of $P_\mathcal{B}$ turns that linear combination into the matrix equation $P_\mathcal{B}\vec{c} = \vec{x}$, which is a standard system.

Q: When computing $[\vec{x}]_\mathcal{B}$ by hand, when is row-reducing $[P_\mathcal{B} \mid \vec{x}]$ preferable to computing $P_\mathcal{B}^{-1}$?
A: Row-reducing is faster for a single $\vec{x}$ because inverting a matrix costs about as much as solving several systems. Compute $P_\mathcal{B}^{-1}$ only when you will reuse it for many different $\vec{x}$.

## 6.6 Change of Basis Between Two Bases

C: If $\mathcal{B}$ and $\mathcal{C}$ are both bases of $\mathbb{R}^n$, the [change-of-coordinates matrix from $\mathcal{B}$ to $\mathcal{C}$] is $P_{\mathcal{C}\leftarrow\mathcal{B}} = P_\mathcal{C}^{-1}P_\mathcal{B}$, where $P_\mathcal{B}$ and $P_\mathcal{C}$ have the respective basis vectors as columns.

C: The change-of-basis relation is $[\vec{x}]_\mathcal{C} = [P_{\mathcal{C}\leftarrow\mathcal{B}}[\vec{x}]_\mathcal{B}]$.

Q: Why does the formula $P_{\mathcal{C}\leftarrow\mathcal{B}} = P_\mathcal{C}^{-1}P_\mathcal{B}$ make intuitive sense?
A: Read right to left: $P_\mathcal{B}$ takes $\mathcal{B}$-coordinates and recovers $\vec{x}$ in standard coordinates, and then $P_\mathcal{C}^{-1}$ converts that standard vector into $\mathcal{C}$-coordinates. Composing these two steps gives the direct $\mathcal{B}$-to-$\mathcal{C}$ conversion.

Q: How are $P_{\mathcal{C}\leftarrow\mathcal{B}}$ and $P_{\mathcal{B}\leftarrow\mathcal{C}}$ related?
A: They are inverses of each other: $P_{\mathcal{B}\leftarrow\mathcal{C}} = (P_{\mathcal{C}\leftarrow\mathcal{B}})^{-1}$. Converting from $\mathcal{B}$ to $\mathcal{C}$ and back must be the identity, so the two matrices undo each other.

C: The inverse of $P_{\mathcal{C}\leftarrow\mathcal{B}}$ is $[P_{\mathcal{B}\leftarrow\mathcal{C}}]$.

Q: What does $P_{\mathcal{C}\leftarrow\mathcal{B}}$ reduce to when $\mathcal{C}$ is the standard basis of $\mathbb{R}^n$?
A: It reduces to $P_\mathcal{B}$ itself, because $P_\mathcal{C} = I$ for the standard basis, so $P_{\mathcal{C}\leftarrow\mathcal{B}} = I^{-1}P_\mathcal{B} = P_\mathcal{B}$.

## 6.7 Polynomial Example

Q: What is the standard basis of $\mathbb{P}_2$, the space of polynomials of degree at most 2?
A: The standard basis is $\mathcal{E} = \{1, t, t^2\}$. Every polynomial of degree $\le 2$ is a unique linear combination of these three.

Q: What are the coordinates of $p(t) = 1 + 2t + t^2$ relative to the standard basis $\mathcal{E} = \{1, t, t^2\}$ of $\mathbb{P}_2$?
A: The coordinates are $[p]_\mathcal{E} = (1, 2, 1)$, because $p(t) = 1\cdot 1 + 2\cdot t + 1\cdot t^2$. The coefficients read directly off the polynomial in standard form.

Q: Why does assigning coordinates to polynomials let us treat $\mathbb{P}_2$ like $\mathbb{R}^3$?
A: The coordinate map $p \mapsto [p]_\mathcal{E}$ sends each polynomial to a unique triple of reals and preserves addition and scaling. So any question about linear combinations of polynomials can be answered by doing the arithmetic on their coordinate triples in $\mathbb{R}^3$.

C: Under the standard basis, $p(t) = a_0 + a_1 t + a_2 t^2$ has coordinate vector $[(a_0, a_1, a_2)]$ in $\mathbb{R}^3$.

## 6.8 Isomorphism

C: A linear, invertible map between vector spaces is called an [isomorphism].

Q: Why is every $n$-dimensional vector space $V$ isomorphic to $\mathbb{R}^n$?
A: Choose any basis $\mathcal{B}$ of $V$ with $n$ vectors. The coordinate map $\vec{x} \mapsto [\vec{x}]_\mathcal{B}$ is linear and bijective, so it is an isomorphism between $V$ and $\mathbb{R}^n$. Dimension alone determines the space up to isomorphism.

Q: What does it mean that $\mathbb{P}_2$ is isomorphic to $\mathbb{R}^3$?
A: There is a linear bijection between them — the coordinate map using $\{1, t, t^2\}$ — so any structural property expressible through linear combinations (independence, span, dimension) transfers between the two. Polynomial problems in $\mathbb{P}_2$ can be solved by working with triples in $\mathbb{R}^3$.

C: Two vector spaces are isomorphic if and only if they have the same [dimension].

Q: Why doesn't the particular isomorphism $V \cong \mathbb{R}^n$ matter for structural questions?
A: Different bases give different isomorphisms, but each one preserves linear structure. So properties like "these vectors are independent" or "this set spans" are invariant — they hold in $V$ iff they hold for the coordinate images in $\mathbb{R}^n$, no matter which basis we chose.

## 6.9 Connection to Linear Systems

Q: Why can every change-of-basis computation be reframed as a linear system?
A: Finding $[\vec{x}]_\mathcal{B}$ means solving $P_\mathcal{B}\vec{c} = \vec{x}$, and converting between bases means solving a chain of such systems. So all of change-of-basis reduces to row reducing augmented matrices of the form $[P_\mathcal{B} \mid \vec{x}]$.

C: Computing $[\vec{x}]_\mathcal{B}$ reduces to row-reducing the augmented matrix $[[P_\mathcal{B} \mid \vec{x}]]$.

Q: Why does the invertible matrix theorem guarantee that $P_\mathcal{B}\vec{c} = \vec{x}$ always has a unique solution?
A: Because $\mathcal{B}$ is a basis, $P_\mathcal{B}$ is square with linearly independent columns, hence invertible. The invertible matrix theorem then guarantees a unique solution $\vec{c} = P_\mathcal{B}^{-1}\vec{x}$ for every right-hand side $\vec{x}$.

## 6.10 Worked Problem

P: Let $\mathcal{B} = \{\vec{b}_1, \vec{b}_2\}$ with $\vec{b}_1 = \begin{pmatrix}1\\1\end{pmatrix}$, $\vec{b}_2 = \begin{pmatrix}1\\-1\end{pmatrix}$, and $\mathcal{C} = \{\vec{c}_1, \vec{c}_2\}$ with $\vec{c}_1 = \begin{pmatrix}2\\0\end{pmatrix}$, $\vec{c}_2 = \begin{pmatrix}0\\1\end{pmatrix}$ be bases of $\mathbb{R}^2$. Compute $P_{\mathcal{C}\leftarrow\mathcal{B}}$, then use it to convert $[\vec{x}]_\mathcal{B} = \begin{pmatrix}3\\1\end{pmatrix}$ into $\mathcal{C}$-coordinates.

S:
**IDENTIFY**: Change-of-basis computation between two non-standard bases of $\mathbb{R}^2$. We need the matrix $P_{\mathcal{C}\leftarrow\mathcal{B}}$, then apply it to a given $\mathcal{B}$-coordinate vector.

**PLAN**:
- Form $P_\mathcal{B}$ with columns $\vec{b}_1, \vec{b}_2$ and $P_\mathcal{C}$ with columns $\vec{c}_1, \vec{c}_2$.
- Compute $P_\mathcal{C}^{-1}$ (easy because $P_\mathcal{C}$ is diagonal).
- Multiply: $P_{\mathcal{C}\leftarrow\mathcal{B}} = P_\mathcal{C}^{-1}P_\mathcal{B}$.
- Apply: $[\vec{x}]_\mathcal{C} = P_{\mathcal{C}\leftarrow\mathcal{B}}[\vec{x}]_\mathcal{B}$.

**EXECUTE**:
1. $P_\mathcal{B} = \begin{pmatrix}1 & 1\\1 & -1\end{pmatrix}$, $P_\mathcal{C} = \begin{pmatrix}2 & 0\\0 & 1\end{pmatrix}$.
2. $P_\mathcal{C}^{-1} = \begin{pmatrix}1/2 & 0\\0 & 1\end{pmatrix}$.
3. $P_{\mathcal{C}\leftarrow\mathcal{B}} = \begin{pmatrix}1/2 & 0\\0 & 1\end{pmatrix}\begin{pmatrix}1 & 1\\1 & -1\end{pmatrix} = \begin{pmatrix}1/2 & 1/2\\1 & -1\end{pmatrix}$.
4. $[\vec{x}]_\mathcal{C} = \begin{pmatrix}1/2 & 1/2\\1 & -1\end{pmatrix}\begin{pmatrix}3\\1\end{pmatrix} = \begin{pmatrix}2\\2\end{pmatrix}$.

**EVALUATE**:
- Sanity check by going through standard coordinates: $\vec{x} = 3\vec{b}_1 + \vec{b}_2 = 3\begin{pmatrix}1\\1\end{pmatrix} + \begin{pmatrix}1\\-1\end{pmatrix} = \begin{pmatrix}4\\2\end{pmatrix}$.
- Now express $\begin{pmatrix}4\\2\end{pmatrix}$ in $\mathcal{C}$: we need $a\vec{c}_1 + b\vec{c}_2 = \begin{pmatrix}2a\\b\end{pmatrix} = \begin{pmatrix}4\\2\end{pmatrix}$, giving $a = 2, b = 2$.
- Matches $[\vec{x}]_\mathcal{C} = (2, 2)$. ✓

## 6.11 Common Pitfalls

Q: Why is it wrong to build $P_\mathcal{B}$ by putting the basis vectors as rows instead of columns?
A: The identity $\vec{x} = P_\mathcal{B}[\vec{x}]_\mathcal{B}$ is a linear combination of basis vectors scaled by the coordinates. A matrix-vector product combines columns, not rows, so the basis vectors must be columns for the formula to work.

Q: Why is $[\vec{x}]_\mathcal{B}$ generally different from $\vec{x}$ even when $V = \mathbb{R}^n$?
A: $[\vec{x}]_\mathcal{B}$ records $\vec{x}$'s components along the $\vec{b}_i$, not along the standard axes. Only when $\mathcal{B}$ is the standard basis do the two tuples coincide; for any other basis, reading $\vec{x}$ and $[\vec{x}]_\mathcal{B}$ as the same vector is a mistake.

Q: If you swap the order of two basis vectors in $\mathcal{B}$, what happens to $[\vec{x}]_\mathcal{B}$ and $P_\mathcal{B}$?
A: The corresponding entries of $[\vec{x}]_\mathcal{B}$ swap, and the corresponding columns of $P_\mathcal{B}$ swap. The vector $\vec{x}$ itself is unchanged — only its tuple representation reshuffles with the basis ordering.
