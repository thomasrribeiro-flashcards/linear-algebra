+++
order = 5
subject = "Math"
tags = ["math", "linear-algebra", "linear-independence", "basis", "dimension", "rank", "rank-nullity"]
+++

# Linear Algebra — Linear Independence, Basis, and Dimension

## 5.1 Linear Dependence and Independence

Q: Why do we care whether a set of vectors is linearly independent?
A: Independence captures whether every vector in the set contributes a genuinely new direction. If vectors are dependent, at least one is redundant — it can be built from the others — which means our "set" has fewer effective dimensions than its size suggests. This matters for describing spaces economically.

C: A set $\{\vec{v}_1, \ldots, \vec{v}_k\}$ is [linearly independent] if the only scalars $c_1, \ldots, c_k$ satisfying $c_1\vec{v}_1 + \cdots + c_k\vec{v}_k = \vec{0}$ are $c_1 = \cdots = c_k = 0$.

C: A set $\{\vec{v}_1, \ldots, \vec{v}_k\}$ is [linearly dependent] if there exist scalars $c_1, \ldots, c_k$, not all zero, such that $c_1\vec{v}_1 + \cdots + c_k\vec{v}_k = \vec{0}$.

Q: Why does "the only combination giving $\vec{0}$ is the trivial one" matter so much?
A: If a nontrivial combination produces $\vec{0}$, we can solve for one vector in terms of the others, proving one vector is redundant. Conversely, if only the trivial combination works, no vector can be written in terms of the others, so every vector genuinely adds a new direction.

Q: If $\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}$ is linearly dependent, what can you conclude?
A: At least one vector in the set is a linear combination of the others. It does not mean every vector is dependent on the others — only that at least one is redundant.

## 5.2 Dependence via the Matrix Equation $A\vec{x} = \vec{0}$

Q: How does linear independence of vectors relate to solutions of $A\vec{x} = \vec{0}$?
A: Place the vectors as columns of a matrix $A$. A linear combination $c_1\vec{v}_1 + \cdots + c_k\vec{v}_k$ equals $A\vec{x}$ where $\vec{x}$ holds the coefficients $c_i$. The combination equals $\vec{0}$ iff $A\vec{x} = \vec{0}$, so independence translates directly into a statement about solutions.

C: The columns of a matrix $A$ are linearly independent iff $A\vec{x} = \vec{0}$ has only the [trivial solution] $\vec{x} = \vec{0}$.

C: The columns of $A$ are linearly dependent iff $A\vec{x} = \vec{0}$ has a [nontrivial solution] (some $\vec{x} \neq \vec{0}$).

Q: Why is testing independence equivalent to row-reducing $A$?
A: Row reduction finds all solutions of $A\vec{x} = \vec{0}$. If every column of $A$ is a pivot column, there are no free variables and only the trivial solution exists (independent). If any column is non-pivot, it corresponds to a free variable, giving nontrivial solutions (dependent).

C: The columns of $A$ are linearly independent iff every column of $A$ is a [pivot column] in its RREF.

## 5.3 Geometric Intuition

Q: When are two vectors in $\mathbb{R}^2$ linearly independent?
A: When they are not parallel, i.e., neither is a scalar multiple of the other. Two parallel vectors lie on a single line, so one is redundant; non-parallel vectors span a 2D plane together.

Q: When are three vectors in $\mathbb{R}^3$ linearly independent?
A: When they are not coplanar. If all three lie in a common plane through the origin, one can be written as a combination of the other two. Three vectors pointing into genuinely different "3D directions" are independent.

C: Two nonzero vectors in $\mathbb{R}^2$ are linearly dependent iff they are [parallel] (scalar multiples of each other).

C: Three nonzero vectors in $\mathbb{R}^3$ are linearly dependent iff they are [coplanar] (all lie in a common plane through the origin).

## 5.4 Special Cases: Zero Vector and Singletons

Q: Why is any set containing $\vec{0}$ automatically linearly dependent?
A: Take $c = 1$ on $\vec{0}$ and $c = 0$ on all other vectors: $1 \cdot \vec{0} + 0 \cdot \vec{v}_1 + \cdots + 0 \cdot \vec{v}_k = \vec{0}$. This is a nontrivial combination (one coefficient is nonzero) yielding $\vec{0}$, which is exactly dependence.

C: Any set of vectors containing the zero vector is automatically linearly [dependent].

Q: When is a set consisting of a single vector $\{\vec{v}\}$ linearly independent?
A: Exactly when $\vec{v} \neq \vec{0}$. The only way $c\vec{v} = \vec{0}$ for $\vec{v} \neq \vec{0}$ is $c = 0$, so the trivial combination is the only one. If $\vec{v} = \vec{0}$, any $c$ works, giving dependence.

C: A single nonzero vector $\{\vec{v}\}$ is linearly [independent].

## 5.5 Too Many Vectors Forces Dependence

Q: Why are any 4 vectors in $\mathbb{R}^3$ automatically linearly dependent?
A: Place them as columns of a $3 \times 4$ matrix $A$. $A\vec{x} = \vec{0}$ has 4 unknowns but at most 3 pivots, so at least one free variable exists, giving a nontrivial solution. More unknowns than equations forces a nontrivial solution.

C: In $\mathbb{R}^n$, any set of more than $n$ vectors is automatically linearly [dependent].

Q: What is the intuition behind "more vectors than ambient dimension forces dependence"?
A: Each truly new independent direction consumes one dimension. A space of dimension $n$ only has room for $n$ independent directions; any extra vector must be built from the ones already present.

## 5.6 Basis

Q: What is a basis of a vector space $V$?
A: A basis of $V$ is a set of vectors in $V$ that is both linearly independent and spans $V$. It is a minimal spanning set and a maximal independent set simultaneously.

C: A set $\mathcal{B} = \{\vec{b}_1, \ldots, \vec{b}_n\}$ is a [basis] of $V$ iff $\mathcal{B}$ spans $V$ and $\mathcal{B}$ is linearly independent.

Q: Why does a basis require BOTH spanning and linear independence?
A: Spanning alone can have redundancy (e.g., three coplanar vectors spanning a plane in $\mathbb{R}^3$ are wasteful). Independence alone may not cover the space (e.g., one vector in $\mathbb{R}^3$ is independent but spans only a line). A basis is the "just right" size: enough to reach every vector, few enough that none is redundant.

Q: What happens if a spanning set is dependent?
A: You can remove at least one vector (the dependent one) and still span the same space. Dependence signals redundancy — you are using more vectors than needed.

Q: What happens if an independent set does not span?
A: You can add at least one vector outside the current span, keeping the set independent. Non-spanning signals missing directions — you need more vectors to reach the whole space.

## 5.7 Standard Basis of $\mathbb{R}^n$

C: The standard basis of $\mathbb{R}^n$ is $\{\vec{e}_1, \ldots, \vec{e}_n\}$, where $\vec{e}_i$ has a [1 in the $i$-th position] and 0 elsewhere.

Q: Why is $\{\vec{e}_1, \vec{e}_2, \vec{e}_3\}$ a basis of $\mathbb{R}^3$?
A: The matrix $[\vec{e}_1 \; \vec{e}_2 \; \vec{e}_3]$ is the identity $I_3$, which has pivots in every column (independence) and every row (spanning). Every vector $(a,b,c)$ equals $a\vec{e}_1 + b\vec{e}_2 + c\vec{e}_3$.

## 5.8 Basis of $\mathbb{P}_n$

C: A basis of $\mathbb{P}_n$ (polynomials of degree at most $n$) is $\{1, t, t^2, \ldots, [t^n]\}$, where $t$ is the polynomial variable.

Q: Why is $\{1, t, t^2, \ldots, t^n\}$ a basis of $\mathbb{P}_n$?
A: Every polynomial of degree $\leq n$ can be written as $a_0 + a_1 t + \cdots + a_n t^n$ (spanning). And $a_0 + a_1 t + \cdots + a_n t^n = 0$ as a polynomial forces each $a_i = 0$ (independence). So the set spans $\mathbb{P}_n$ and is independent.

## 5.9 Uniqueness of Representation

Q: Why is the representation of a vector in a given basis unique?
A: Suppose $\vec{v} = c_1\vec{b}_1 + \cdots + c_n\vec{b}_n = d_1\vec{b}_1 + \cdots + d_n\vec{b}_n$. Subtracting gives $(c_1 - d_1)\vec{b}_1 + \cdots + (c_n - d_n)\vec{b}_n = \vec{0}$. Since the basis is independent, each $c_i - d_i = 0$, so $c_i = d_i$.

C: In a basis $\mathcal{B} = \{\vec{b}_1, \ldots, \vec{b}_n\}$, every vector $\vec{v} \in V$ has a [unique] representation $\vec{v} = c_1\vec{b}_1 + \cdots + c_n\vec{b}_n$.

Q: What are coordinates of $\vec{v}$ relative to a basis $\mathcal{B}$?
A: The unique scalars $(c_1, \ldots, c_n)$ such that $\vec{v} = c_1\vec{b}_1 + \cdots + c_n\vec{b}_n$. They form the coordinate vector $[\vec{v}]_\mathcal{B}$, which depends on the chosen basis.

## 5.10 Dimension

Q: Why is the number of vectors in a basis well-defined (independent of which basis you pick)?
A: Any two bases of the same vector space $V$ must have the same number of elements. If one had more vectors, it would be forced to be dependent (too many vectors for the space). So all bases have the same size — that common number is the dimension.

C: The [dimension] of a vector space $V$, written $\dim V$, is the number of vectors in any basis of $V$.

C: $\dim(\mathbb{R}^n) = [n]$.

C: $\dim(\mathbb{P}_n) = [n+1]$, because the basis $\{1, t, \ldots, t^n\}$ has $n+1$ elements.

C: By convention, $\dim(\{\vec{0}\}) = [0]$, since the zero subspace has empty basis.

## 5.11 Basis Theorem

Q: What does the Basis Theorem say about a space $V$ of dimension $n$?
A: In $V$ with $\dim V = n$: (1) any $n$ linearly independent vectors automatically span $V$, and (2) any $n$ vectors that span $V$ are automatically linearly independent. Once you have the "right number," one property forces the other.

Q: Why does the Basis Theorem save work?
A: To check if $n$ vectors form a basis of an $n$-dimensional space, you only need to verify ONE condition (independence OR spanning), not both. The dimension constraint guarantees the other half for free.

C: In a space of dimension $n$, any [$n$ linearly independent] vectors automatically span the space.

C: In a space of dimension $n$, any $n$ [spanning] vectors are automatically linearly independent.

## 5.12 Basis for the Column Space

Q: How do you find a basis for $\text{Col}(A)$?
A: Row-reduce $A$ to find pivot positions. The pivot columns of the original matrix $A$ (not of the RREF) form a basis of $\text{Col}(A)$. Row operations change the column space but preserve linear dependence relations among columns, so pivot columns in RREF correspond to independent columns in $A$.

C: A basis for $\text{Col}(A)$ is the set of [pivot columns of $A$] (taken from the original matrix, not the RREF).

Q: Why do we take pivot columns from $A$ itself, not from its RREF?
A: Row operations alter the column space — columns of RREF are generally different vectors than columns of $A$. But row operations preserve which columns are linear combinations of which, so the pivot positions identify the correct columns to grab from the original $A$.

## 5.13 Basis for the Null Space

Q: How do you find a basis for $\text{Nul}(A)$?
A: Solve $A\vec{x} = \vec{0}$ by row-reducing to RREF and writing $\vec{x}$ in parametric vector form, with one parameter per free variable. The vectors multiplying each free parameter form a basis of $\text{Nul}(A)$.

C: A basis for $\text{Nul}(A)$ has one vector per [free variable] in $A\vec{x} = \vec{0}$.

Q: Why is the parametric-form method guaranteed to produce a basis of $\text{Nul}(A)$?
A: Every null-space vector is a combination of the parameter vectors (spanning). Each parameter controls its own free variable independently, so setting the combination to $\vec{0}$ forces every parameter to 0 (independence). Spanning plus independence equals a basis.

## 5.14 Basis for the Row Space

Q: How do you find a basis for $\text{Row}(A)$?
A: Row-reduce $A$ to RREF (or any echelon form). The nonzero rows of the result form a basis of $\text{Row}(A)$. Row operations preserve the row space, and nonzero rows of an echelon form are automatically linearly independent.

C: A basis for $\text{Row}(A)$ is the set of [nonzero rows] of the RREF of $A$.

Q: Why can we take rows from RREF (but not columns)?
A: Row operations preserve the row space exactly — each new row is a combination of old rows, and vice versa. But row operations generally change the column space, which is why column-space bases must use the original matrix's pivot columns.

## 5.15 Rank

Q: What is the rank of a matrix?
A: The rank of $A$ is the dimension of its column space, which equals the dimension of its row space, which equals the number of pivot positions in the RREF of $A$. All three give the same number.

C: $\text{rank}(A) = \dim(\text{Col}\,A) = \dim(\text{Row}\,A) = $ number of [pivots] in the RREF of $A$.

Q: Why does $\dim(\text{Col}\,A) = \dim(\text{Row}\,A)$?
A: Both equal the number of pivot positions. Each pivot contributes one pivot column (giving a Col basis vector) and one nonzero row in RREF (giving a Row basis vector). The pivot count is a single number shared by both spaces.

## 5.16 Rank-Nullity Theorem

Q: State the Rank-Nullity Theorem.
A: For an $m \times n$ matrix $A$: $\text{rank}(A) + \dim(\text{Nul}\,A) = n$, where $n$ is the number of columns.

C: For an $m \times n$ matrix $A$: $\text{rank}(A) + \dim(\text{Nul}\,A) = [n]$, where $n$ is the number of columns of $A$.

Q: Why is the Rank-Nullity Theorem true?
A: Each column of $A$ corresponds to a variable in $A\vec{x} = \vec{0}$. Every variable is either basic (pivot column, contributes to rank) or free (contributes to nullity). Since pivot + free = total, rank + nullity equals the number of columns.

C: In $A\vec{x} = \vec{0}$: number of [pivot variables] + number of free variables = number of columns.

Q: If $A$ is $5 \times 8$ with rank 3, what is $\dim(\text{Nul}\,A)$?
A: By Rank-Nullity: $3 + \dim(\text{Nul}\,A) = 8$, so $\dim(\text{Nul}\,A) = 5$. There are $8 - 3 = 5$ free variables.

## 5.17 The Invertible Matrix Theorem (Expanded)

Q: For a square $n \times n$ matrix $A$, what are equivalent ways of saying $A$ is invertible?
A: $A$ is invertible iff $\det A \neq 0$ iff the columns of $A$ are linearly independent iff the columns of $A$ span $\mathbb{R}^n$ iff $\text{rank}(A) = n$ iff $\text{Nul}(A) = \{\vec{0}\}$ iff $A\vec{x} = \vec{0}$ has only the trivial solution iff $A$ row-reduces to $I_n$.

C: For a square $n \times n$ matrix, $A$ is invertible iff its columns are linearly [independent].

C: For a square $n \times n$ matrix, $A$ is invertible iff $\text{rank}(A) = [n]$ (full rank).

C: For a square $n \times n$ matrix, $A$ is invertible iff $\text{Nul}(A) = [\{\vec{0}\}]$ (trivial null space).

C: For a square $n \times n$ matrix, $A$ is invertible iff the columns of $A$ [span] $\mathbb{R}^n$.

Q: Why do all these conditions collapse into one for square matrices?
A: For a square $n \times n$ matrix, "independent columns," "spanning columns," and "full rank $n$" each say the RREF is $I_n$ — the same condition phrased three ways. Each pivot claims one row and one column simultaneously, so no-free-variables (injectivity) forces every-row-reached (surjectivity).

Q: For a non-square matrix, which Invertible-Matrix-Theorem equivalences fail?
A: Independence and spanning decouple. An $m \times n$ matrix with $m > n$ can have independent columns without spanning $\mathbb{R}^m$; one with $m < n$ can span $\mathbb{R}^m$ without independent columns. The "invertible" framework applies only to square matrices.

## 5.18 Worked Example: Full Analysis of a Matrix

P: Let $A = \begin{bmatrix} 1 & 2 & 0 & 1 \\ 2 & 4 & 1 & 4 \\ 3 & 6 & 2 & 7 \end{bmatrix}$. Find $\text{rank}(A)$, and give a basis for $\text{Col}(A)$, $\text{Row}(A)$, and $\text{Nul}(A)$.

S:
**IDENTIFY**: Complete subspace analysis of a $3 \times 4$ matrix — need rank and bases for column, row, and null spaces.

**PLAN**:
- Row-reduce $A$ to RREF to locate pivot positions.
- Rank = number of pivots.
- $\text{Col}(A)$ basis = pivot columns of the ORIGINAL $A$.
- $\text{Row}(A)$ basis = nonzero rows of the RREF.
- $\text{Nul}(A)$ basis = parametric-form vectors from solving $A\vec{x} = \vec{0}$.

**EXECUTE**:

Step 1. Row-reduce. $R_2 \leftarrow R_2 - 2R_1$, $R_3 \leftarrow R_3 - 3R_1$:
$$\begin{bmatrix} 1 & 2 & 0 & 1 \\ 0 & 0 & 1 & 2 \\ 0 & 0 & 2 & 4 \end{bmatrix}$$
Then $R_3 \leftarrow R_3 - 2R_2$:
$$\text{RREF} = \begin{bmatrix} 1 & 2 & 0 & 1 \\ 0 & 0 & 1 & 2 \\ 0 & 0 & 0 & 0 \end{bmatrix}$$

Step 2. Pivots are in columns 1 and 3, so $\text{rank}(A) = 2$.

Step 3. $\text{Col}(A)$ basis: take columns 1 and 3 of ORIGINAL $A$:
$$\left\{ \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 2 \end{bmatrix} \right\}.$$

Step 4. $\text{Row}(A)$ basis: nonzero rows of RREF:
$$\{(1, 2, 0, 1), \; (0, 0, 1, 2)\}.$$

Step 5. $\text{Nul}(A)$: free variables are $x_2, x_4$. From RREF: $x_1 = -2x_2 - x_4$, $x_3 = -2x_4$. Set $x_2 = s$, $x_4 = t$:
$$\vec{x} = s\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + t\begin{bmatrix} -1 \\ 0 \\ -2 \\ 1 \end{bmatrix}.$$
Basis: $\left\{\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ -2 \\ 1 \end{bmatrix}\right\}$.

**EVALUATE**:
- Rank-Nullity check: $\text{rank}(A) + \dim(\text{Nul}\,A) = 2 + 2 = 4 = $ number of columns. ✓
- $\text{Col}(A)$ basis has 2 vectors in $\mathbb{R}^3$ — consistent with rank 2.
- $\text{Row}(A)$ basis has 2 vectors in $\mathbb{R}^4$ — also consistent with rank 2.
- Verify null-space vectors: $A \cdot (-2, 1, 0, 0)^T = -2\vec{a}_1 + \vec{a}_2 = \vec{0}$ ✓ (since column 2 $= 2 \cdot$ column 1).
