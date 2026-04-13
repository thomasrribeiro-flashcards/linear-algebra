+++
order = 2
tags = ["math", "linear-algebra", "matrix-algebra", "matrix-multiplication", "inverse", "transpose", "elementary-matrices"]
+++

# Linear Algebra — Matrix Algebra

## 2.1 Matrix Addition and Scalar Multiplication

Q: Why must two matrices have the same shape to be added?
A: Addition is defined entry-wise, meaning the $(i,j)$ entry of $A+B$ is $a_{ij}+b_{ij}$. This requires every entry of $A$ to correspond to an entry of $B$ at the same position, which is only possible when the matrices have identical dimensions. Shape mismatch would leave entries without partners, so the operation would be undefined.

C: Matrix addition is performed [entry-wise], so $(A+B)_{ij} = a_{ij} + b_{ij}$, where $a_{ij}$ and $b_{ij}$ are the entries of $A$ and $B$ in row $i$, column $j$.

C: For two matrices $A$ and $B$ to be added, they must have [the same shape] (same number of rows and same number of columns).

C: For a scalar $c$ and matrix $A$, the scalar product is defined by $(cA)_{ij} = [c\,a_{ij}]$, where $a_{ij}$ is the $(i,j)$ entry of $A$ and $c$ is any real number.

Q: Why is matrix addition commutative and associative?
A: Both properties are inherited directly from real-number arithmetic because addition is defined entry-wise. Since $a_{ij}+b_{ij}=b_{ij}+a_{ij}$ for every entry, $A+B=B+A$, and the same reasoning gives associativity. Matrix addition behaves like vector addition on a grid of numbers.

## 2.2 The Matrix-Vector Product $A\vec{x}$

Q: Before seeing the definition, predict: if $A$ is $m\times n$, what should the dimensions of $\vec{x}$ and $A\vec{x}$ be?
A: $\vec{x}$ should have $n$ entries so it can pair with the $n$ columns (or rows) of $A$, and $A\vec{x}$ should have $m$ entries, matching the number of rows of $A$. The product eats an $n$-vector and outputs an $m$-vector.

Q: Why is $A\vec{x}$ defined as a linear combination of the columns of $A$?
A: This definition captures the geometric meaning of a matrix: the columns are the images of the standard basis vectors, so multiplying by $\vec{x}$ combines those images weighted by the entries of $\vec{x}$. It also makes $A\vec{x}=\vec{b}$ directly express "is $\vec{b}$ reachable from the columns of $A$?" This framing unifies linear systems, span, and linear transformations.

C: If $A$ has columns $\vec{a}_1,\dots,\vec{a}_n$ and $\vec{x}=(x_1,\dots,x_n)^T$, then $A\vec{x} = [x_1\vec{a}_1 + x_2\vec{a}_2 + \cdots + x_n\vec{a}_n]$, a linear combination of the columns of $A$ weighted by the entries of $\vec{x}$.

C: The $i$-th entry of $A\vec{x}$ equals the [dot product] of the $i$-th row of $A$ with $\vec{x}$, where $A$ is $m\times n$ and $\vec{x}\in\mathbb{R}^n$.

C: For the product $A\vec{x}$ to be defined, the number of columns of $A$ must equal [the number of entries of $\vec{x}$].

Q: Why do the "columns" view and "rows" view of $A\vec{x}$ give the same answer?
A: Expanding a linear combination of columns entry-by-entry produces exactly the row-dot-product formula. The columns view shows WHY the product matters (reachability, span), while the rows view shows HOW to compute it quickly. Both are equivalent algebraic rearrangements of the same sum $\sum_j a_{ij}x_j$.

## 2.3 The Matrix Equation $A\vec{x} = \vec{b}$

Q: Why is the system of linear equations with coefficient matrix $A$ and right-hand side $\vec{b}$ equivalent to the single equation $A\vec{x}=\vec{b}$?
A: Each row of $A\vec{x}$ is the dot product of a row of $A$ with $\vec{x}$, which equals the left-hand side of one scalar equation. Setting $A\vec{x}=\vec{b}$ entry-by-entry reproduces every scalar equation simultaneously. So the matrix equation is a compact encoding of the entire linear system.

C: The matrix equation $A\vec{x}=\vec{b}$ has a solution if and only if $\vec{b}$ is a [linear combination] of the columns of $A$, where $A$ is the coefficient matrix and $\vec{b}$ is the right-hand side vector.

C: The homogeneous equation $A\vec{x}=\vec{0}$ always has at least the [trivial] solution $\vec{x}=\vec{0}$.

## 2.4 Matrix Multiplication $AB$

Q: Before seeing the formal definition, predict: if $A$ is $m\times n$ and $B$ is $n\times p$, what should the shape of $AB$ be?
A: $AB$ should be $m\times p$. Each column of $B$ is an $n$-vector that $A$ can act on, producing an $m$-vector output; there are $p$ such columns, giving $p$ output columns of size $m$.

C: The product $AB$ is defined column-by-column: the $j$-th column of $AB$ equals [$A\vec{b}_j$], where $\vec{b}_j$ is the $j$-th column of $B$.

C: If $A$ is $m\times n$ and $B$ is $n\times p$, then $AB$ is a matrix of size [$m\times p$].

C: For the product $AB$ to be defined, the number of columns of $A$ must equal [the number of rows of $B$].

Q: How can the $(i,j)$ entry of $AB$ be computed directly?
A: It equals the dot product of the $i$-th row of $A$ with the $j$-th column of $B$: $(AB)_{ij} = \sum_{k=1}^{n} a_{ik}b_{kj}$, where $a_{ik}$ is the $(i,k)$ entry of $A$ and $b_{kj}$ is the $(k,j)$ entry of $B$. This formula follows from the column-by-column definition combined with the row-dot-product view of $A\vec{x}$.

## 2.5 Why Matrix Multiplication Is Defined That Way

Q: Why is matrix multiplication defined using column-by-column application rather than entry-wise?
A: Matrices represent linear transformations, and composition of linear maps must correspond to matrix multiplication. If $A$ represents a map $T_A$ and $B$ represents $T_B$, then applying $T_A$ after $T_B$ to a vector $\vec{x}$ gives $A(B\vec{x})=(AB)\vec{x}$ exactly when $AB$ is defined column-wise. Entry-wise multiplication would not respect composition, making it useless for the central purpose of matrices.

C: Matrix multiplication corresponds to [composition of linear transformations]: if $A$ represents $T_A$ and $B$ represents $T_B$, then $AB$ represents the map $T_A \circ T_B$.

Q: Why does the order $AB$ correspond to "$B$ first, then $A$"?
A: The vector $\vec{x}$ is written on the right, so $(AB)\vec{x} = A(B\vec{x})$: $B$ acts first on $\vec{x}$, then $A$ acts on the result. This right-to-left reading is a consequence of placing inputs to the right of the operator, matching function notation $f(g(x))$.

## 2.6 Properties of Matrix Multiplication

C: Matrix multiplication is [associative]: $(AB)C = A(BC)$ whenever the products are defined, where $A$, $B$, $C$ are matrices of compatible sizes.

C: Matrix multiplication is [distributive] over addition: $A(B+C) = AB + AC$ and $(A+B)C = AC + BC$, where all sums and products are assumed to be defined.

C: Matrix multiplication is in general [not commutative]: $AB \neq BA$ even when both products are defined.

Q: Why is matrix multiplication not commutative?
A: Because it represents composition of linear maps, and composing "rotate then reflect" generally differs from "reflect then rotate." Algebraically, $AB$ and $BA$ need not even have the same shape when $A$ and $B$ are non-square, and when they do, the entries mix rows and columns differently. Commutativity is the exception (e.g., with $I$ or powers of a single matrix), not the rule.

P: Give a $2\times 2$ counterexample showing $AB \neq BA$.

S:
**IDENTIFY**: Construct two square matrices whose products in opposite orders differ.

**PLAN**: Pick simple $2\times 2$ matrices with distinct structure so the cross terms do not cancel.

**EXECUTE**:
Let $A=\begin{pmatrix}1 & 1\\ 0 & 1\end{pmatrix}$ and $B=\begin{pmatrix}1 & 0\\ 1 & 1\end{pmatrix}$.
- $AB = \begin{pmatrix}1\cdot 1 + 1\cdot 1 & 1\cdot 0 + 1\cdot 1\\ 0\cdot 1 + 1\cdot 1 & 0\cdot 0 + 1\cdot 1\end{pmatrix} = \begin{pmatrix}2 & 1\\ 1 & 1\end{pmatrix}$.
- $BA = \begin{pmatrix}1\cdot 1 + 0\cdot 0 & 1\cdot 1 + 0\cdot 1\\ 1\cdot 1 + 1\cdot 0 & 1\cdot 1 + 1\cdot 1\end{pmatrix} = \begin{pmatrix}1 & 1\\ 1 & 2\end{pmatrix}$.

**EVALUATE**: $AB \neq BA$, confirming non-commutativity. The off-diagonal pattern shifted, which is typical when shearing composes with itself in different orders.

## 2.7 The Identity Matrix $I_n$

C: The [identity matrix] $I_n$ is the $n\times n$ matrix with $1$'s on the main diagonal and $0$'s elsewhere.

C: For any $m\times n$ matrix $A$, we have $I_m A = A$ and $A I_n = [A]$, where $I_k$ is the $k\times k$ identity.

Q: Why is $I_n$ called the multiplicative identity for $n\times n$ matrices?
A: Because $I_n A = A I_n = A$ for every $n\times n$ matrix $A$, it plays the role of $1$ in matrix algebra. Geometrically, $I_n$ represents the linear map that leaves every vector unchanged, so composing with it does nothing.

## 2.8 The Transpose $A^T$

C: The [transpose] $A^T$ of an $m\times n$ matrix $A$ is the $n\times m$ matrix whose $(i,j)$ entry equals $a_{ji}$, the $(j,i)$ entry of $A$.

Q: Why does transposing swap rows and columns?
A: The transpose reinterprets the rows of $A$ as columns (and vice versa), which geometrically corresponds to swapping the input and output roles of the linear map. This role-swap is what makes identities like $(A\vec{x})\cdot\vec{y} = \vec{x}\cdot(A^T\vec{y})$ hold, tying the transpose to the dot product.

C: The transpose satisfies $(A+B)^T = [A^T + B^T]$, where $A$ and $B$ are matrices of the same shape.

C: The transpose of a product reverses order: $(AB)^T = [B^T A^T]$, where $A$ is $m\times n$ and $B$ is $n\times p$.

Q: Why does $(AB)^T = B^T A^T$ rather than $A^T B^T$?
A: The product $AB$ sends an input through $B$ first, then $A$; transposing reverses the flow of information, so the transposed map sends an input through $A^T$ first, then $B^T$ — but with the new orientation, that composition is written $B^T A^T$. Shape alone confirms it: if $A$ is $m\times n$ and $B$ is $n\times p$, then $AB$ is $m\times p$, so $(AB)^T$ is $p\times m$, matching $B^T(p\times n)\cdot A^T(n\times m)$.

C: $(A^T)^T = [A]$, for any matrix $A$.

## 2.9 The Matrix Inverse

C: An $n\times n$ matrix $A$ is [invertible] (or nonsingular) if there exists an $n\times n$ matrix $A^{-1}$ such that $A A^{-1} = A^{-1} A = I_n$, where $I_n$ is the $n\times n$ identity.

Q: Why must an inverse satisfy BOTH $AA^{-1}=I$ and $A^{-1}A=I$ in the definition?
A: Conceptually, $A^{-1}$ must undo $A$ whether applied before or after it. For square matrices, one of these equations actually implies the other, but stating both makes the two-sided "undo" nature of the inverse explicit and matches the algebraic idea of a reciprocal in noncommutative settings.

C: A matrix that is not invertible is called [singular].

Q: Why must a matrix be square to have an inverse (in the standard sense)?
A: If $A$ is $m\times n$ with $m\neq n$, then $A$ maps between spaces of different dimensions and cannot be a bijection, so no two-sided inverse can exist. The equation $AA^{-1}=I_m$ and $A^{-1}A=I_n$ can only hold simultaneously when $m=n$ so both identities have the same size. Non-square matrices admit only one-sided or generalized inverses.

## 2.10 When Does an Inverse Exist

C: A square matrix $A$ is invertible if and only if the homogeneous equation $A\vec{x}=\vec{0}$ has [only the trivial solution] $\vec{x}=\vec{0}$.

Q: Why does "only the trivial solution to $A\vec{x}=\vec{0}$" characterize invertibility?
A: If $A\vec{v}=\vec{0}$ for some nonzero $\vec{v}$, then $A$ collapses $\vec{v}$ to zero, so no map can recover $\vec{v}$ from $\vec{0}$ and $A$ cannot be inverted. Conversely, if the only solution is $\vec{v}=\vec{0}$, then $A$ is injective on $\mathbb{R}^n$, hence bijective (since domain and codomain have equal dimension), and a two-sided inverse exists. Invertibility is thus equivalent to "no nonzero vector is killed."

C: For a square matrix $A$, invertibility is equivalent to $A$ being [row-equivalent] to the identity matrix $I_n$.

## 2.11 Computing $A^{-1}$ by Gauss-Jordan

Q: Why does running Gauss-Jordan on the augmented matrix $[A\mid I]$ yield $[I\mid A^{-1}]$ when $A$ is invertible?
A: Each row operation corresponds to left-multiplication by an elementary matrix $E_k$, and the full sequence gives $E_r\cdots E_1 A = I$, so $E_r\cdots E_1 = A^{-1}$. Applying the same sequence to the right block transforms $I$ into $E_r\cdots E_1\cdot I = A^{-1}$. Gauss-Jordan simultaneously builds $A^{-1}$ by accumulating the row operations that reduce $A$ to $I$.

C: To compute $A^{-1}$, row-reduce the augmented matrix $[A\mid I]$ to reduced row echelon form; the result is [$[I\mid A^{-1}]$] when $A$ is invertible.

C: If Gauss-Jordan on $[A\mid I]$ fails to produce $I$ on the left (i.e., the left block has a zero row in RREF), then $A$ is [singular] (not invertible).

P: Compute $A^{-1}$ by Gauss-Jordan for $A=\begin{pmatrix}1 & 2\\ 3 & 4\end{pmatrix}$.

S:
**IDENTIFY**: Matrix inversion via Gauss-Jordan on the augmented matrix $[A\mid I]$.

**PLAN**:
- Form $[A\mid I_2] = \left[\begin{array}{cc|cc}1 & 2 & 1 & 0\\ 3 & 4 & 0 & 1\end{array}\right]$.
- Use row operations to reduce the left block to $I_2$; the right block becomes $A^{-1}$.

**EXECUTE**:
1. $R_2 \leftarrow R_2 - 3R_1$: $\left[\begin{array}{cc|cc}1 & 2 & 1 & 0\\ 0 & -2 & -3 & 1\end{array}\right]$.
2. $R_2 \leftarrow -\tfrac{1}{2}R_2$: $\left[\begin{array}{cc|cc}1 & 2 & 1 & 0\\ 0 & 1 & \tfrac{3}{2} & -\tfrac{1}{2}\end{array}\right]$.
3. $R_1 \leftarrow R_1 - 2R_2$: $\left[\begin{array}{cc|cc}1 & 0 & -2 & 1\\ 0 & 1 & \tfrac{3}{2} & -\tfrac{1}{2}\end{array}\right]$.
4. Read off $A^{-1} = \begin{pmatrix}-2 & 1\\ \tfrac{3}{2} & -\tfrac{1}{2}\end{pmatrix}$.

**EVALUATE**: Check $AA^{-1} = \begin{pmatrix}1 & 2\\ 3 & 4\end{pmatrix}\begin{pmatrix}-2 & 1\\ \tfrac{3}{2} & -\tfrac{1}{2}\end{pmatrix} = \begin{pmatrix}1 & 0\\ 0 & 1\end{pmatrix}$. The $2\times 2$ formula gives $\frac{1}{1\cdot 4 - 2\cdot 3}\begin{pmatrix}4 & -2\\ -3 & 1\end{pmatrix} = \frac{1}{-2}\begin{pmatrix}4 & -2\\ -3 & 1\end{pmatrix} = \begin{pmatrix}-2 & 1\\ \tfrac{3}{2} & -\tfrac{1}{2}\end{pmatrix}$, matching.

## 2.12 The $2\times 2$ Inverse Formula

C: For $A=\begin{pmatrix}a & b\\ c & d\end{pmatrix}$, the inverse is $A^{-1} = [\tfrac{1}{ad-bc}\begin{pmatrix}d & -b\\ -c & a\end{pmatrix}]$, provided $ad-bc\neq 0$, where $a,b,c,d$ are the entries of $A$.

C: The $2\times 2$ matrix $A=\begin{pmatrix}a & b\\ c & d\end{pmatrix}$ is invertible if and only if [$ad-bc\neq 0$], where $ad-bc$ is the determinant of $A$.

Q: Why does the $2\times 2$ inverse formula swap the diagonal and negate the off-diagonal?
A: Multiplying $A$ by $\begin{pmatrix}d & -b\\ -c & a\end{pmatrix}$ yields $(ad-bc)I$, so dividing by $ad-bc$ produces $I$. The swap comes from pairing each row of $A$ with a column engineered to kill the unwanted cross terms while preserving the diagonal, a miniature cofactor construction.

## 2.13 Properties of Inverses

C: The inverse of a product reverses order: $(AB)^{-1} = [B^{-1}A^{-1}]$, where $A$ and $B$ are invertible $n\times n$ matrices.

Q: Why does $(AB)^{-1} = B^{-1}A^{-1}$ rather than $A^{-1}B^{-1}$?
A: To undo "apply $B$, then $A$", you must first undo $A$ and then undo $B$, in reverse order — like removing socks and shoes. Algebraically, $(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AA^{-1} = I$, verifying the order. Order-reversal is a universal feature of inverses in noncommutative settings.

C: The inverse of the transpose equals the transpose of the inverse: $(A^T)^{-1} = [(A^{-1})^T]$, for any invertible matrix $A$.

C: The inverse of the inverse is the original: $(A^{-1})^{-1} = [A]$, for any invertible matrix $A$.

C: For an invertible matrix $A$ and nonzero scalar $c$, $(cA)^{-1} = [\tfrac{1}{c}A^{-1}]$.

## 2.14 Elementary Matrices

C: An [elementary matrix] is a matrix obtained from the identity $I_n$ by performing a single elementary row operation.

Q: Why does left-multiplying a matrix $A$ by an elementary matrix $E$ perform the corresponding row operation on $A$?
A: The rows of $EA$ are linear combinations of the rows of $A$ dictated by the rows of $E$. Since $E$ differs from $I$ only by the row operation encoded in it, $EA$ differs from $A$ by exactly that same row operation. This makes elementary matrices the algebraic embodiment of row operations.

C: Every elementary matrix is [invertible], and its inverse is itself an elementary matrix corresponding to the reverse row operation.

Q: Why is every invertible matrix a product of elementary matrices?
A: If $A$ is invertible, Gauss-Jordan reduces $A$ to $I$ via a sequence of row operations $E_r\cdots E_1 A = I$, so $A = E_1^{-1}\cdots E_r^{-1}$. Each $E_k^{-1}$ is itself elementary, so $A$ factors entirely into elementaries. This factorization provides both a structural description of invertible matrices and a practical tool for proofs.

C: If $A$ is invertible, then $A = E_1 E_2 \cdots E_k$ for some [elementary] matrices $E_1,\dots,E_k$.

## 2.15 Block Matrices

C: A [block matrix] is a matrix partitioned into rectangular submatrices (blocks) that are treated as single entries for algebraic operations.

Q: Why are block matrices useful?
A: They allow large computations to be organized in terms of smaller, meaningful submatrices, often reflecting structure in the underlying problem (e.g., coupling between subsystems). Block addition and block multiplication follow the same formulas as scalar entry operations, provided the blocks have compatible sizes. This gives a powerful bookkeeping tool for proofs and algorithms.

C: Block matrices can be multiplied using the same row-column formula as ordinary matrices, provided the block sizes are [compatible] (inner block dimensions match).
