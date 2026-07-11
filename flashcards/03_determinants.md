+++
order = 3
subject = "mathematics"
tags = ["math", "linear-algebra", "determinants", "cofactor-expansion", "cramer", "adjugate"]
+++

# Linear Algebra — Determinants

## 3.1 The $2\times 2$ Determinant

Q: Why do we want a single number associated with a square matrix?
A: Many properties of a matrix — whether it is invertible, how it scales volumes, and whether a linear system has a unique solution — can be summarized in one scalar. The determinant packages these properties into one number that is easy to check (e.g., nonzero vs. zero) without solving the system.

C: For a $2\times 2$ matrix $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the determinant is $\det(A) = [ad - bc]$, where $a,b,c,d$ are the real entries of $A$.

Q: Geometrically, what does $\det\begin{pmatrix} a & b \\ c & d \end{pmatrix}$ represent?
A: It is the signed area of the parallelogram spanned by the column vectors $\begin{pmatrix}a\\c\end{pmatrix}$ and $\begin{pmatrix}b\\d\end{pmatrix}$ in $\mathbb{R}^2$. A positive sign means the columns form a right-handed (counterclockwise) pair; a negative sign means the orientation is reversed.

C: If $\det(A) = 0$ for a $2\times 2$ matrix $A$, then the two column vectors of $A$ are [parallel (linearly dependent)], so the parallelogram they span collapses to a line segment with zero area.

Q: Compute $\det\begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$.
A: $\det = (3)(4) - (1)(2) = 12 - 2 = 10$. Here $a=3$, $b=1$, $c=2$, $d=4$, so $ad-bc = 10$.

## 3.2 Why Determinants Matter

Q: What are the two primary roles the determinant plays for a square matrix $A$?
A: First, it detects invertibility: $A$ is invertible if and only if $\det(A) \neq 0$. Second, $|\det(A)|$ is the factor by which the linear map $\vec{x} \mapsto A\vec{x}$ scales $n$-dimensional volume. These two uses — a test and a geometric scale factor — appear throughout the rest of linear algebra.

C: The linear map $\vec{x} \mapsto A\vec{x}$ scales $n$-dimensional volume by the factor $[|\det(A)|]$, where $A$ is an $n\times n$ matrix.

Q: Before reading the formal rule, predict: if $\det(A) = 0$, can $A\vec{x} = \vec{b}$ have a unique solution for every $\vec{b}$?
A: No. A zero determinant means $A$ collapses space onto a lower-dimensional subspace, so the map cannot be one-to-one or onto. Unique solutions for every $\vec{b}$ require an invertible $A$, which requires $\det(A)\neq 0$.

## 3.3 Minors and Cofactors

C: For an $n\times n$ matrix $A$, the $(i,j)$ [minor] $M_{ij}$ is the determinant of the $(n-1)\times(n-1)$ matrix obtained by deleting row $i$ and column $j$ of $A$.

C: For an $n\times n$ matrix $A$, the $(i,j)$ cofactor is $C_{ij} = [(-1)^{i+j} M_{ij}]$, where $M_{ij}$ is the $(i,j)$ minor of $A$.

Q: Why is the sign factor $(-1)^{i+j}$ included in the cofactor?
A: It encodes the alternating signs required so that cofactor expansion along any row or column gives the same determinant. Without the sign, orientation information (which is tied to swapping rows) would be lost, and the expansion formula would not agree across different rows.

C: The sign pattern of cofactors for a $3\times 3$ matrix is $\begin{pmatrix} + & - & + \\ - & + & - \\ + & - & + \end{pmatrix}$, because the sign of $C_{ij}$ is $[(-1)^{i+j}]$, depending on the position $(i,j)$.

## 3.4 Cofactor Expansion

C: Cofactor expansion along row $i$: $\det(A) = [\sum_{j=1}^{n} a_{ij} C_{ij}]$, where $a_{ij}$ is the $(i,j)$ entry of $A$ and $C_{ij}$ is its cofactor.

Q: Along which row or column should you expand to minimize work?
A: Choose the row or column with the most zero entries. Each zero entry $a_{ij}$ contributes $0 \cdot C_{ij} = 0$ to the sum, so you only need to compute cofactors for the nonzero entries. This reduces the number of $(n-1)\times(n-1)$ subdeterminants you must evaluate.

Q: Why does cofactor expansion give the same value along any row or column?
A: The determinant is a multilinear, alternating function of the rows (equivalently, columns). These two properties force the cofactor expansion to produce the same scalar no matter which row or column is chosen. Expansion is just a way of unpacking the same underlying function.

## 3.5 The $3\times 3$ Determinant

P: Compute $\det(A)$ for $A = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 4 & 5 \\ 1 & 0 & 6 \end{pmatrix}$ by cofactor expansion.

S:
**IDENTIFY**: Compute a $3\times 3$ determinant using cofactor expansion, where $A$ has entries $a_{ij}$ with $i,j \in \{1,2,3\}$.

**PLAN**: Expand along row 2, since it contains a zero ($a_{21}=0$), reducing the number of minors to compute. Use $\det(A) = \sum_{j=1}^{3} a_{2j} C_{2j}$ with $C_{2j} = (-1)^{2+j} M_{2j}$.

**EXECUTE**:
1. $a_{21}=0$, so that term vanishes.
2. $a_{22}=4$, $C_{22} = (+1)\det\begin{pmatrix}1&3\\1&6\end{pmatrix} = 6 - 3 = 3$. Contribution: $4\cdot 3 = 12$.
3. $a_{23}=5$, $C_{23} = (-1)\det\begin{pmatrix}1&2\\1&0\end{pmatrix} = -(0 - 2) = 2$. Contribution: $5\cdot 2 = 10$.
4. $\det(A) = 0 + 12 + 10 = 22$.

**EVALUATE**: Cross-check by expanding along column 1: $a_{11}=1$, $M_{11}=\det\begin{pmatrix}4&5\\0&6\end{pmatrix}=24$; $a_{21}=0$; $a_{31}=1$, $M_{31}=\det\begin{pmatrix}2&3\\4&5\end{pmatrix}=10-12=-2$, with sign $(+1)$. So $\det(A) = 1\cdot 24 - 0 + 1\cdot(-2) = 22$. ✓

## 3.6 Determinant of a Triangular Matrix

C: If $A$ is an $n\times n$ triangular matrix (upper or lower), then $\det(A) = [\prod_{i=1}^{n} a_{ii}]$, the product of the diagonal entries $a_{ii}$.

Q: Why is the determinant of a triangular matrix just the product of diagonal entries?
A: Repeatedly expand along the column (for upper triangular) or row (for lower triangular) that contains only one nonzero entry — the diagonal entry. Each expansion contributes one diagonal factor and leaves a smaller triangular matrix, so the process multiplies the diagonal entries together.

Q: What is $\det\begin{pmatrix} 2 & 7 & -1 \\ 0 & 3 & 5 \\ 0 & 0 & 4 \end{pmatrix}$?
A: $2 \cdot 3 \cdot 4 = 24$. The matrix is upper triangular, so the determinant is the product of diagonal entries $2$, $3$, and $4$.

C: A consequence: the determinant of the $n\times n$ identity matrix $I_n$ is $[1]$, since all diagonal entries equal $1$.

## 3.7 Effect of Row Operations on the Determinant

C: Row swap: if $B$ is obtained from $A$ by swapping two rows, then $\det(B) = [-\det(A)]$, where $A,B$ are $n\times n$ matrices.

C: Row scaling: if $B$ is obtained from $A$ by multiplying one row by a scalar $k$, then $\det(B) = [k\det(A)]$.

C: Row replacement: if $B$ is obtained from $A$ by adding a multiple of one row to a different row, then $\det(B) = [\det(A)]$ (the determinant is unchanged).

Q: Why does row replacement ($R_i \to R_i + k R_j$) leave the determinant unchanged?
A: The determinant is a multilinear, alternating function of the rows. Multilinearity splits the new determinant into $\det(A) + k\det(A')$, where $A'$ has row $j$ in place of row $i$ — so $A'$ has two equal rows and determinant $0$. Only $\det(A)$ survives.

Q: Why does swapping two rows flip the sign of the determinant?
A: The determinant is an alternating function of its rows: exchanging two rows multiplies the value by $-1$. This is equivalent to saying that a matrix with two equal rows has determinant zero (apply the swap to itself).

## 3.8 Computing the Determinant by Row Reduction

Q: Why is row reduction usually more efficient than cofactor expansion for large matrices?
A: Cofactor expansion on an $n\times n$ matrix costs on the order of $n!$ operations, which explodes quickly. Row reduction to triangular form runs in roughly $n^3$ operations; once triangular, the determinant is just the product of diagonal entries, adjusted for any row swaps and scalings used along the way.

P: Compute $\det(A)$ for $A = \begin{pmatrix} 2 & 4 & 2 \\ 1 & 3 & 1 \\ 3 & 7 & 5 \end{pmatrix}$ using row reduction.

S:
**IDENTIFY**: $3\times 3$ determinant via row reduction to upper triangular form, tracking how each row operation affects the determinant.

**PLAN**: Use row replacements (no sign change, no scaling) as much as possible; if rows are swapped, flip sign; if a row is scaled, divide out the factor. Then multiply the final diagonal entries.

**EXECUTE**:
1. $R_1 \leftrightarrow R_2$: new matrix $\begin{pmatrix}1&3&1\\2&4&2\\3&7&5\end{pmatrix}$; this swap introduces a factor of $-1$.
2. $R_2 \to R_2 - 2R_1$: $\begin{pmatrix}1&3&1\\0&-2&0\\3&7&5\end{pmatrix}$; determinant unchanged.
3. $R_3 \to R_3 - 3R_1$: $\begin{pmatrix}1&3&1\\0&-2&0\\0&-2&2\end{pmatrix}$; determinant unchanged.
4. $R_3 \to R_3 - R_2$: $\begin{pmatrix}1&3&1\\0&-2&0\\0&0&2\end{pmatrix}$; determinant unchanged.
5. Diagonal product: $1 \cdot (-2) \cdot 2 = -4$. Include the sign flip from step 1: $\det(A) = -(-4) = 4$.

**EVALUATE**: Cross-check by cofactor expansion along column 3: $a_{13}=2$, $a_{23}=1$, $a_{33}=5$. $C_{13}=\det\begin{pmatrix}1&3\\3&7\end{pmatrix}=7-9=-2$; $C_{23}=-\det\begin{pmatrix}2&4\\3&7\end{pmatrix}=-(14-12)=-2$; $C_{33}=\det\begin{pmatrix}2&4\\1&3\end{pmatrix}=6-4=2$. Sum: $2(-2) + 1(-2) + 5(2) = -4 - 2 + 10 = 4$. ✓

## 3.9 Determinant and Invertibility

C: An $n\times n$ matrix $A$ is invertible if and only if $\det(A) \neq [0]$.

Q: Why does $\det(A)=0$ imply $A$ is singular (not invertible)?
A: If $A$ is invertible, it row-reduces to $I_n$, which has determinant $1$. Row operations multiply the determinant by nonzero factors ($\pm 1$ for swaps, $k\neq 0$ for scalings, $1$ for replacements). Working backward, a nonzero $\det(I_n)$ forces $\det(A)\neq 0$. Contrapositively, $\det(A)=0$ means $A$ cannot row-reduce to $I_n$, so it is singular.

Q: Geometrically, why is a matrix with $\det(A)=0$ not invertible?
A: A zero determinant means the linear map $\vec{x}\mapsto A\vec{x}$ collapses volume to zero, i.e., it squashes $\mathbb{R}^n$ onto a lower-dimensional subspace. No linear map can un-collapse that lost dimension, so no inverse exists.

## 3.10 Multiplicative Property

C: For $n\times n$ matrices $A$ and $B$, $\det(AB) = [\det(A)\det(B)]$.

Q: Why is $\det(AB) = \det(A)\det(B)$ geometrically sensible?
A: The map $AB$ first applies $B$, scaling volume by $|\det(B)|$, then applies $A$, scaling volume by $|\det(A)|$. Total volume scaling is the product $|\det(A)||\det(B)|$. Orientation signs also multiply, giving $\det(AB) = \det(A)\det(B)$.

C: If $A$ is invertible, then $\det(A^{-1}) = [1/\det(A)]$, because $\det(A)\det(A^{-1}) = \det(I) = 1$.

Q: What does the multiplicative property say about $\det(A^k)$ for integer $k\ge 0$?
A: $\det(A^k) = (\det A)^k$. Applying $\det(AB)=\det(A)\det(B)$ repeatedly to $A^k = A\cdot A\cdots A$ gives a product of $k$ copies of $\det(A)$. For $k=0$, $A^0=I$, and $(\det A)^0 = 1 = \det(I)$.

## 3.11 Determinant of the Transpose

C: For any square matrix $A$, $\det(A^T) = [\det(A)]$, where $A^T$ is the transpose of $A$.

Q: Why does $\det(A^T) = \det(A)$ let us expand along columns as freely as along rows?
A: Expanding $\det(A)$ along row $i$ of $A$ is the same as expanding $\det(A^T)$ along column $i$ of $A^T$. Since the two determinants are equal, every row-expansion rule for $A$ is also a column-expansion rule for $A$. This is why row operations and column operations affect $\det(A)$ the same way.

## 3.12 Determinant as Signed Volume in $\mathbb{R}^n$

C: For an $n\times n$ matrix $A$ with columns $\vec{a}_1,\dots,\vec{a}_n$, the quantity $|\det(A)|$ equals the [$n$-dimensional volume] of the parallelepiped spanned by those column vectors in $\mathbb{R}^n$.

Q: What is the meaning of the sign of $\det(A)$ for an $n\times n$ matrix?
A: The sign encodes orientation: $\det(A) > 0$ means the columns form a basis with the same orientation as the standard basis $\vec{e}_1,\dots,\vec{e}_n$ (right-handed in $\mathbb{R}^3$); $\det(A) < 0$ means the basis has the opposite (reversed) orientation.

Q: If a linear map has $\det(A) = -2$, what does that say geometrically?
A: It doubles volume ($|\det|=2$) and flips orientation (negative sign). In $\mathbb{R}^3$, a right-handed object would become left-handed after the map, in addition to doubling in volume.

## 3.13 Cramer's Rule

Q: When is Cramer's rule applicable?
A: When solving the linear system $A\vec{x} = \vec{b}$ with $A$ an $n\times n$ invertible matrix (i.e., $\det(A)\neq 0$). It gives each unknown $x_i$ directly in terms of determinants, without performing full row reduction.

C: Cramer's rule: for $A\vec{x} = \vec{b}$ with $\det(A)\neq 0$, $x_i = [\det(A_i)/\det(A)]$, where $A_i$ is the matrix obtained from $A$ by replacing its $i$-th column with $\vec{b}$.

Q: Why is Cramer's rule rarely used for large systems despite its elegance?
A: Computing $n+1$ determinants of $n\times n$ matrices is much more expensive than one row reduction of the augmented matrix. Cramer's rule is mainly useful for small systems, theoretical derivations, and symbolic answers where a closed-form expression for $x_i$ is desired.

P: Solve for $x_1$ in the system $\begin{cases} 2x_1 + x_2 = 5 \\ x_1 + 3x_2 = 10 \end{cases}$ using Cramer's rule.

S:
**IDENTIFY**: Apply Cramer's rule to $A\vec{x}=\vec{b}$, with $A = \begin{pmatrix}2&1\\1&3\end{pmatrix}$ and $\vec{b} = \begin{pmatrix}5\\10\end{pmatrix}$; need $x_1$.

**PLAN**: Verify $\det(A)\neq 0$, form $A_1$ by replacing column $1$ of $A$ with $\vec{b}$, then $x_1 = \det(A_1)/\det(A)$.

**EXECUTE**:
1. $\det(A) = 2\cdot 3 - 1\cdot 1 = 5 \neq 0$.
2. $A_1 = \begin{pmatrix}5&1\\10&3\end{pmatrix}$, $\det(A_1) = 5\cdot 3 - 1\cdot 10 = 5$.
3. $x_1 = 5/5 = 1$.

**EVALUATE**: Substitute: $x_2$ from the first equation is $5 - 2(1) = 3$; check the second: $1 + 3(3) = 10$. ✓

## 3.14 Adjugate and the Inverse Formula

C: The [adjugate] (also called classical adjoint) of an $n\times n$ matrix $A$, written $\operatorname{adj}(A)$, is the transpose of the cofactor matrix: $\operatorname{adj}(A)_{ij} = C_{ji}$, where $C_{ji}$ is the $(j,i)$ cofactor of $A$.

C: If $A$ is an $n\times n$ invertible matrix, then $A^{-1} = [\frac{1}{\det(A)}\operatorname{adj}(A)]$.

Q: Why does the adjugate formula require $\det(A)\neq 0$?
A: The formula involves dividing by $\det(A)$. If $\det(A)=0$, the division is undefined — consistent with the fact that $A$ is not invertible in that case, so no inverse exists to produce.

Q: What is the key identity linking $A$ and its adjugate?
A: $A \cdot \operatorname{adj}(A) = \operatorname{adj}(A) \cdot A = \det(A)\, I_n$, where $I_n$ is the $n\times n$ identity. Dividing by $\det(A)$ (when nonzero) yields the inverse formula $A^{-1} = \operatorname{adj}(A)/\det(A)$.

P: Use the adjugate formula to compute $A^{-1}$ for $A = \begin{pmatrix} 2 & 1 \\ 3 & 4 \end{pmatrix}$.

S:
**IDENTIFY**: Find the inverse of a $2\times 2$ matrix using $A^{-1} = \frac{1}{\det A}\operatorname{adj}(A)$, where entries of $A$ are labeled $a=2$, $b=1$, $c=3$, $d=4$.

**PLAN**: For a $2\times 2$ matrix $\begin{pmatrix}a&b\\c&d\end{pmatrix}$, the adjugate is $\begin{pmatrix}d&-b\\-c&a\end{pmatrix}$. Compute $\det(A)$, form the adjugate, divide.

**EXECUTE**:
1. $\det(A) = (2)(4) - (1)(3) = 5$.
2. $\operatorname{adj}(A) = \begin{pmatrix}4 & -1 \\ -3 & 2\end{pmatrix}$.
3. $A^{-1} = \frac{1}{5}\begin{pmatrix}4 & -1 \\ -3 & 2\end{pmatrix} = \begin{pmatrix}4/5 & -1/5 \\ -3/5 & 2/5\end{pmatrix}$.

**EVALUATE**: Check $A A^{-1} = I$: top-left entry $(2)(4/5) + (1)(-3/5) = 8/5 - 3/5 = 1$ ✓; top-right $(2)(-1/5)+(1)(2/5) = -2/5+2/5=0$ ✓.

## 3.15 Combined Method: $4\times 4$ Determinant

P: Compute $\det(A)$ for $A = \begin{pmatrix} 1 & 2 & 0 & 1 \\ 2 & 5 & 1 & 3 \\ 0 & 1 & 2 & 4 \\ 3 & 6 & 1 & 5 \end{pmatrix}$ using a combination of row reduction and cofactor expansion.

S:
**IDENTIFY**: Compute a $4\times 4$ determinant efficiently, where direct cofactor expansion would require four $3\times 3$ subdeterminants; entries are labeled $a_{ij}$ for $i,j\in\{1,\dots,4\}$.

**PLAN**:
- First use row replacements to create more zeros in column 1 (they don't change $\det$).
- Then expand along the column with the most zeros, giving a single $3\times 3$ determinant to compute.
- Finish the $3\times 3$ by cofactor expansion or $2\times 2$ reduction.

**EXECUTE**:
1. Start from $A$; determinant-preserving row replacements:
   - $R_2 \to R_2 - 2R_1$: row 2 becomes $(0,\,1,\,1,\,1)$.
   - $R_4 \to R_4 - 3R_1$: row 4 becomes $(0,\,0,\,1,\,2)$.
   - Row 3 already has a zero in column 1.
2. The matrix is now $\begin{pmatrix} 1 & 2 & 0 & 1 \\ 0 & 1 & 1 & 1 \\ 0 & 1 & 2 & 4 \\ 0 & 0 & 1 & 2 \end{pmatrix}$, with the same determinant as $A$.
3. Expand along column 1: only $a_{11}=1$ is nonzero. Sign $(-1)^{1+1}=+1$. So $\det(A) = 1\cdot \det(M_{11})$, where $M_{11} = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 2 & 4 \\ 0 & 1 & 2 \end{pmatrix}$.
4. Compute $\det(M_{11})$ by expansion along column 1:
   - $a_{11}=1$, minor $\det\begin{pmatrix}2&4\\1&2\end{pmatrix}=4-4=0$; contribution $+1\cdot 0 = 0$.
   - $a_{21}=1$, minor $\det\begin{pmatrix}1&1\\1&2\end{pmatrix}=2-1=1$; sign $(-1)^{2+1}=-1$; contribution $-1\cdot 1 = -1$.
   - $a_{31}=0$; contribution $0$.
   - $\det(M_{11}) = 0 - 1 + 0 = -1$.
5. $\det(A) = 1 \cdot (-1) = -1$.

**EVALUATE**: Cross-check by another row: continue reducing in step 2 to triangular form. $R_3 \to R_3 - R_2$: row 3 becomes $(0,0,1,3)$. $R_4 \to R_4 - R_3$ (new): row 4 becomes $(0,0,0,-1)$. The matrix is now upper triangular with diagonal $(1,1,1,-1)$; product is $-1$. ✓ Since only row replacements were used, no sign or scaling corrections are needed, confirming $\det(A) = -1$.
