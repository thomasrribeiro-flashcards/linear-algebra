+++
order = 10
subject = "Mathematics"
tags = ["math", "linear-algebra", "gram-schmidt", "qr-decomposition", "orthonormal-basis"]
+++

# Linear Algebra — Gram-Schmidt and QR Decomposition

## 10.1 The Problem

Q: Why do we want an orthonormal basis for a subspace instead of just any basis?
A: Orthonormal bases make many computations dramatically simpler and more stable. Projections reduce to single inner products, coordinates of a vector are found by direct dot products (no linear system to solve), and least-squares problems collapse to simple formulas. Orthonormal bases also produce numerically stable algorithms because rounding errors do not amplify through ill-conditioned systems.

Q: What problem does the Gram-Schmidt process solve?
A: Given any basis $\{\vec{x}_1,\ldots,\vec{x}_n\}$ of a subspace $W$, it produces an orthogonal (and after normalization, orthonormal) basis of the same subspace $W$. The span is preserved exactly, so any vector expressible in the old basis is expressible in the new one.

C: Gram-Schmidt converts an arbitrary basis into an [orthonormal] basis of the same subspace.

Q: Why does having orthonormal columns make projection onto a subspace easy?
A: If $\{\vec{q}_1,\ldots,\vec{q}_k\}$ is an orthonormal basis of $W$, the projection of $\vec{v}$ onto $W$ is simply $\sum_{i=1}^k (\vec{v}\cdot\vec{q}_i)\,\vec{q}_i$. No matrix inversion or linear system is required — each coefficient is a single inner product.

Q: Why is Gram-Schmidt relevant to least squares?
A: Least squares requires projecting a target vector onto the column space of a matrix $A$. An orthonormal basis of that column space (produced by Gram-Schmidt, or equivalently the $Q$ in $A=QR$) turns the projection into trivial inner products and avoids solving the normal equations directly.

## 10.2 Gram-Schmidt Idea

Q: What is the core geometric idea of the Gram-Schmidt process?
A: Take each input vector $\vec{x}_k$ in turn, and subtract off its component lying in the span of the already-orthogonalized vectors $\vec{v}_1,\ldots,\vec{v}_{k-1}$. What remains is orthogonal to all of them. Keeping the leftover piece builds up an orthogonal basis one vector at a time.

C: In Gram-Schmidt, each new orthogonal vector $\vec{v}_k$ is obtained by subtracting from $\vec{x}_k$ its [projection onto the span of the previous $\vec{v}_j$].

Q: Why must Gram-Schmidt be applied to a linearly independent set?
A: If $\vec{x}_k$ lies in the span of $\vec{x}_1,\ldots,\vec{x}_{k-1}$, then after subtracting its projection onto that span the leftover is $\vec{0}$, which cannot be normalized and cannot be part of a basis. Linear independence guarantees every $\vec{v}_k$ is nonzero.

Q: Before seeing the formula, predict: if the first input vector $\vec{x}_1$ is already what we want to keep, how should Gram-Schmidt treat it?
A: It should leave $\vec{x}_1$ essentially untouched — there are no previous vectors to subtract projections onto, so $\vec{v}_1 = \vec{x}_1$.

## 10.3 Gram-Schmidt Formulas

C: The first Gram-Schmidt vector is $\vec{v}_1 = [\vec{x}_1]$, where $\vec{x}_1$ is the first input basis vector.

C: The Gram-Schmidt recursion is $\vec{v}_k = \vec{x}_k - \sum_{j<k}[\frac{\vec{x}_k\cdot\vec{v}_j}{\vec{v}_j\cdot\vec{v}_j}]\vec{v}_j$, where $\vec{x}_k$ is the $k$-th input vector and $\vec{v}_j$ are the previously computed orthogonal vectors.

Q: In the Gram-Schmidt formula $\vec{v}_k = \vec{x}_k - \sum_{j<k}\frac{\vec{x}_k\cdot\vec{v}_j}{\vec{v}_j\cdot\vec{v}_j}\vec{v}_j$, what does the coefficient $\frac{\vec{x}_k\cdot\vec{v}_j}{\vec{v}_j\cdot\vec{v}_j}$ represent?
A: It is the scalar coefficient of the orthogonal projection of $\vec{x}_k$ onto the line spanned by $\vec{v}_j$. Multiplying by $\vec{v}_j$ gives the actual projection vector, and summing over $j<k$ gives the projection of $\vec{x}_k$ onto the span of all earlier $\vec{v}_j$.

Q: Why do we divide by $\vec{v}_j\cdot\vec{v}_j$ rather than just by $\|\vec{v}_j\|$ in the Gram-Schmidt formula?
A: Because the $\vec{v}_j$ are orthogonal but not yet normalized. The projection of $\vec{x}_k$ onto an un-normalized $\vec{v}_j$ is $\frac{\vec{x}_k\cdot\vec{v}_j}{\vec{v}_j\cdot\vec{v}_j}\vec{v}_j$ — the denominator $\|\vec{v}_j\|^2 = \vec{v}_j\cdot\vec{v}_j$ compensates for $\vec{v}_j$'s length.

Q: After Gram-Schmidt produces orthogonal vectors $\vec{v}_1,\ldots,\vec{v}_n$, how do we obtain the orthonormal vectors $\vec{q}_1,\ldots,\vec{q}_n$?
A: Divide each by its norm: $\vec{q}_k = \vec{v}_k/\|\vec{v}_k\|$. This rescales each to unit length while preserving direction, so orthogonality is maintained and each $\vec{q}_k$ has length 1.

C: To normalize an orthogonal vector $\vec{v}_k$, compute $\vec{q}_k = [\vec{v}_k/\|\vec{v}_k\|]$, where $\|\vec{v}_k\|$ is the Euclidean norm of $\vec{v}_k$.

## 10.4 Normalizing At The End vs At Each Step

Q: What is the difference between "classical" Gram-Schmidt that normalizes at the end versus a version that normalizes at each step?
A: Mathematically they produce the same orthonormal basis. In the end-normalization version, we keep un-normalized $\vec{v}_j$ throughout and divide by $\vec{v}_j\cdot\vec{v}_j$ in each projection; at the end we rescale to get $\vec{q}_j = \vec{v}_j/\|\vec{v}_j\|$. In the each-step version we normalize immediately to $\vec{q}_j$, so projections simplify to $(\vec{x}_k\cdot\vec{q}_j)\vec{q}_j$ (no denominator).

Q: Why is the projection formula simpler when we normalize at each step?
A: Because $\vec{q}_j\cdot\vec{q}_j = 1$, the denominator in $\frac{\vec{x}_k\cdot\vec{q}_j}{\vec{q}_j\cdot\vec{q}_j}$ disappears. The projection of $\vec{x}_k$ onto $\vec{q}_j$ is just $(\vec{x}_k\cdot\vec{q}_j)\,\vec{q}_j$.

C: If we normalize at each Gram-Schmidt step, the projection onto $\vec{q}_j$ is simply $[(\vec{x}_k\cdot\vec{q}_j)\vec{q}_j]$, where $\vec{q}_j$ is the unit vector in the direction of $\vec{v}_j$.

## 10.5 Span Preservation

Q: What key span-preservation property holds at every stage of Gram-Schmidt?
A: For every $k$, $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\} = \text{span}\{\vec{x}_1,\ldots,\vec{x}_k\}$. So the orthogonal basis spans the same nested sequence of subspaces as the original basis.

C: At every step $k$ of Gram-Schmidt, $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\} = [\text{span}\{\vec{x}_1,\ldots,\vec{x}_k\}]$, where $\vec{x}_i$ are the input vectors and $\vec{v}_i$ the orthogonalized ones.

Q: Why is the nested span equality $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\} = \text{span}\{\vec{x}_1,\ldots,\vec{x}_k\}$ true?
A: Because $\vec{v}_k = \vec{x}_k - (\text{linear combination of }\vec{v}_1,\ldots,\vec{v}_{k-1})$, so $\vec{x}_k$ lies in $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\}$ and conversely $\vec{v}_k$ lies in $\text{span}\{\vec{x}_1,\ldots,\vec{x}_k\}$. The two sets of $k$ vectors generate the same subspace.

Q: Why does the nested span property matter for QR decomposition?
A: It means that the first $k$ columns of $Q$ span the same subspace as the first $k$ columns of $A$. This is precisely what forces $R$ to be upper-triangular — column $k$ of $A$ can be written using only $\vec{q}_1,\ldots,\vec{q}_k$, so entries of $R$ below the diagonal are zero.

## 10.6 QR Decomposition

C: The QR decomposition factors a matrix $A$ as $A = [QR]$, where $Q$ has orthonormal columns and $R$ is upper-triangular.

Q: What are the defining properties of the factors in $A = QR$?
A: $Q$ is a matrix whose columns form an orthonormal basis of the column space of $A$, equivalently $Q^TQ = I$. $R$ is upper-triangular with positive diagonal entries. The factorization exists uniquely for any matrix $A$ with linearly independent columns.

C: In the QR decomposition, $Q$ has orthonormal columns satisfying $[Q^TQ = I]$, where $I$ is the identity matrix.

C: In the QR decomposition, $R$ is [upper-triangular] with positive diagonal entries.

Q: Why must $R$ be upper-triangular in a QR decomposition?
A: Because column $k$ of $A$ lies in the span of $\vec{q}_1,\ldots,\vec{q}_k$ (the Gram-Schmidt span property). So $\vec{a}_k = R_{1k}\vec{q}_1 + \cdots + R_{kk}\vec{q}_k$, with no contribution from $\vec{q}_{k+1},\ldots,\vec{q}_n$. Entries of $R$ below the diagonal are forced to be zero.

Q: Why are the diagonal entries of $R$ chosen positive?
A: The $k$-th diagonal entry is $R_{kk} = \|\vec{v}_k\|$, the length of the $k$-th Gram-Schmidt vector before normalization. Lengths are nonnegative, and for a linearly independent input they are strictly positive. This sign convention also makes the QR factorization unique.

## 10.7 Connecting Gram-Schmidt to QR

Q: How are the columns of $Q$ related to Gram-Schmidt?
A: The columns of $Q$ are exactly the orthonormal vectors $\vec{q}_1,\ldots,\vec{q}_n$ produced by running Gram-Schmidt on the columns $\vec{a}_1,\ldots,\vec{a}_n$ of $A$. So Gram-Schmidt and $Q$ are two names for the same output.

C: In $A=QR$, the entry $R_{jk}$ equals $[\vec{q}_j\cdot\vec{a}_k]$, where $\vec{q}_j$ is the $j$-th column of $Q$ and $\vec{a}_k$ is the $k$-th column of $A$.

Q: Why is $R_{jk} = \vec{q}_j\cdot\vec{a}_k$ for $j\le k$?
A: Since $Q^TQ = I$, multiplying $A = QR$ on the left by $Q^T$ gives $Q^TA = R$. The $(j,k)$ entry of $Q^TA$ is the inner product of the $j$-th row of $Q^T$ (which is $\vec{q}_j$) with the $k$-th column of $A$ (which is $\vec{a}_k$), so $R_{jk} = \vec{q}_j\cdot\vec{a}_k$.

C: From $A = QR$ and $Q^TQ=I$, we can recover $R$ by the identity $R = [Q^TA]$.

Q: What is the $k$-th diagonal entry $R_{kk}$ in terms of Gram-Schmidt quantities?
A: $R_{kk} = \|\vec{v}_k\|$, the norm of the $k$-th unnormalized Gram-Schmidt vector. Equivalently, $R_{kk}$ is the length of the component of $\vec{a}_k$ orthogonal to the span of $\vec{a}_1,\ldots,\vec{a}_{k-1}$.

## 10.8 Uniqueness

Q: Under what conditions is the QR decomposition unique?
A: For any matrix $A$ with linearly independent columns, there is exactly one factorization $A = QR$ in which $Q$ has orthonormal columns and $R$ is upper-triangular with strictly positive diagonal entries. Without the sign convention, each column of $Q$ and the corresponding row of $R$ could be simultaneously negated.

C: The QR decomposition is unique when $R$ is required to have [positive diagonal entries] and $A$ has linearly independent columns.

Q: Why does fixing the sign of the diagonal of $R$ uniquely determine $Q$ and $R$?
A: Because flipping the sign of $\vec{q}_k$ flips the sign of the entire $k$-th row of $R$, including the diagonal. Insisting $R_{kk}>0$ removes this ambiguity for each column, leaving only one valid choice of $Q$ and $R$.

## 10.9 Why QR Is Useful

Q: How does QR simplify solving a least-squares problem $A\vec{x}\approx\vec{b}$?
A: Substitute $A=QR$ into the normal equations. Since $Q^TQ = I$, the normal equations reduce to $R\vec{x} = Q^T\vec{b}$, which is an upper-triangular system. It is solved by a single back-substitution, avoiding the numerically poor step of forming $A^TA$.

C: Using $A = QR$, the least-squares solution to $A\vec{x}\approx\vec{b}$ satisfies the triangular system $[R\vec{x} = Q^T\vec{b}]$.

Q: Why is solving $R\vec{x} = Q^T\vec{b}$ numerically preferable to solving the normal equations $A^TA\vec{x} = A^T\vec{b}$?
A: Forming $A^TA$ squares the condition number of $A$, amplifying rounding errors. Using QR avoids this: $Q$ is perfectly conditioned (orthonormal columns) and $R$ inherits $A$'s conditioning without squaring it. The QR-based solution is therefore far more accurate for ill-conditioned $A$.

Q: What is the QR algorithm for eigenvalues (at a conceptual level)?
A: It iteratively factors $A_k = Q_kR_k$ and forms $A_{k+1} = R_kQ_k$. Under mild conditions, $A_k$ converges to an upper-triangular (or block-triangular) matrix whose diagonal reveals the eigenvalues of the original $A$. This is the standard method for computing eigenvalues of dense matrices.

C: The [QR algorithm] computes eigenvalues by repeatedly factoring $A_k = Q_kR_k$ and forming $A_{k+1} = R_kQ_k$.

## 10.10 Computing QR From Gram-Schmidt

Q: What is the step-by-step recipe to compute $A = QR$ from Gram-Schmidt?
A: (1) Set $\vec{v}_1=\vec{a}_1$ and $\vec{q}_1 = \vec{v}_1/\|\vec{v}_1\|$. (2) For each subsequent column $\vec{a}_k$, compute $\vec{v}_k = \vec{a}_k - \sum_{j<k}(\vec{a}_k\cdot\vec{q}_j)\vec{q}_j$, then $\vec{q}_k = \vec{v}_k/\|\vec{v}_k\|$. (3) Assemble $Q = [\vec{q}_1\,\cdots\,\vec{q}_n]$ and set $R_{jk}=\vec{q}_j\cdot\vec{a}_k$ for $j\le k$ (zero below the diagonal).

C: In the Gram-Schmidt build of $R$, the diagonal entry is $R_{kk} = [\|\vec{v}_k\|]$, the length of the $k$-th unnormalized orthogonal vector.

C: In the Gram-Schmidt build of $R$, the off-diagonal entry $R_{jk}$ for $j<k$ equals $[\vec{a}_k\cdot\vec{q}_j]$, where $\vec{a}_k$ is the $k$-th column of $A$ and $\vec{q}_j$ is the $j$-th orthonormal vector.

## 10.11 Modified Gram-Schmidt

Q: What does modified Gram-Schmidt change about the classical algorithm?
A: Instead of computing $\vec{v}_k = \vec{a}_k - \sum_{j<k}(\vec{a}_k\cdot\vec{q}_j)\vec{q}_j$ all at once using the original $\vec{a}_k$, modified Gram-Schmidt subtracts projections one at a time, updating the working vector after each subtraction. Each inner product is taken against the most recently updated vector.

C: Modified Gram-Schmidt is numerically more [stable] than classical Gram-Schmidt.

Q: Why is modified Gram-Schmidt numerically more stable than classical Gram-Schmidt?
A: In classical Gram-Schmidt, rounding errors from earlier projections get reused when computing later inner products with the original $\vec{a}_k$, letting errors accumulate and producing $\vec{q}_k$ that are not truly orthogonal. In the modified version each subtraction uses the already-corrected intermediate vector, so error does not amplify the way it does in the classical form.

Q: How do the outputs of classical and modified Gram-Schmidt compare in exact arithmetic?
A: In exact arithmetic they produce identical $Q$ and $R$. They differ only in finite-precision floating-point arithmetic, where modified Gram-Schmidt preserves orthogonality of the computed $\vec{q}_k$ much better.

## 10.12 Worked Procedure

P: Given $\vec{a}_1=(1,1,0)$, $\vec{a}_2=(1,0,1)$, $\vec{a}_3=(0,1,1)$ in $\mathbb{R}^3$, apply Gram-Schmidt to obtain an orthonormal basis, then extract $Q$ and $R$ for $A=[\vec{a}_1\,\vec{a}_2\,\vec{a}_3]$.

S:
**IDENTIFY**: Gram-Schmidt applied to three linearly independent vectors in $\mathbb{R}^3$, followed by assembly of the QR factorization $A=QR$ with $Q$ orthonormal and $R$ upper-triangular with positive diagonal.

**PLAN**:
- Set $\vec{v}_1=\vec{a}_1$, normalize to $\vec{q}_1$.
- For $k=2,3$, compute $\vec{v}_k = \vec{a}_k - \sum_{j<k}(\vec{a}_k\cdot\vec{q}_j)\vec{q}_j$, then normalize.
- Build $Q$ by stacking $\vec{q}_1,\vec{q}_2,\vec{q}_3$ as columns.
- Build $R$ with $R_{kk}=\|\vec{v}_k\|$ and $R_{jk}=\vec{a}_k\cdot\vec{q}_j$ for $j<k$.

**EXECUTE**:
1. $\vec{v}_1=(1,1,0)$, $\|\vec{v}_1\|=\sqrt{2}$, so $\vec{q}_1=\tfrac{1}{\sqrt{2}}(1,1,0)$.
2. $\vec{a}_2\cdot\vec{q}_1 = \tfrac{1}{\sqrt{2}}(1+0+0) = \tfrac{1}{\sqrt{2}}$. Then $\vec{v}_2 = (1,0,1) - \tfrac{1}{\sqrt{2}}\cdot\tfrac{1}{\sqrt{2}}(1,1,0) = (1,0,1) - (\tfrac{1}{2},\tfrac{1}{2},0) = (\tfrac{1}{2},-\tfrac{1}{2},1)$. $\|\vec{v}_2\| = \sqrt{\tfrac{1}{4}+\tfrac{1}{4}+1} = \sqrt{\tfrac{3}{2}}$. So $\vec{q}_2 = \tfrac{1}{\sqrt{6}}(1,-1,2)$.
3. $\vec{a}_3\cdot\vec{q}_1 = \tfrac{1}{\sqrt{2}}(0+1+0) = \tfrac{1}{\sqrt{2}}$. $\vec{a}_3\cdot\vec{q}_2 = \tfrac{1}{\sqrt{6}}(0-1+2) = \tfrac{1}{\sqrt{6}}$. Then $\vec{v}_3 = (0,1,1) - \tfrac{1}{\sqrt{2}}\cdot\tfrac{1}{\sqrt{2}}(1,1,0) - \tfrac{1}{\sqrt{6}}\cdot\tfrac{1}{\sqrt{6}}(1,-1,2) = (0,1,1) - (\tfrac{1}{2},\tfrac{1}{2},0) - (\tfrac{1}{6},-\tfrac{1}{6},\tfrac{1}{3}) = (-\tfrac{2}{3},\tfrac{2}{3},\tfrac{2}{3})$. $\|\vec{v}_3\| = \sqrt{3\cdot\tfrac{4}{9}} = \tfrac{2}{\sqrt{3}}$. So $\vec{q}_3 = \tfrac{1}{\sqrt{3}}(-1,1,1)$.
4. Assemble $Q = \begin{pmatrix}1/\sqrt{2} & 1/\sqrt{6} & -1/\sqrt{3}\\ 1/\sqrt{2} & -1/\sqrt{6} & 1/\sqrt{3}\\ 0 & 2/\sqrt{6} & 1/\sqrt{3}\end{pmatrix}$.
5. $R_{11}=\|\vec{v}_1\|=\sqrt{2}$, $R_{22}=\|\vec{v}_2\|=\sqrt{3/2}$, $R_{33}=\|\vec{v}_3\|=2/\sqrt{3}$. $R_{12}=\vec{a}_2\cdot\vec{q}_1=1/\sqrt{2}$, $R_{13}=\vec{a}_3\cdot\vec{q}_1=1/\sqrt{2}$, $R_{23}=\vec{a}_3\cdot\vec{q}_2=1/\sqrt{6}$. So $R = \begin{pmatrix}\sqrt{2} & 1/\sqrt{2} & 1/\sqrt{2}\\ 0 & \sqrt{3/2} & 1/\sqrt{6}\\ 0 & 0 & 2/\sqrt{3}\end{pmatrix}$.

**EVALUATE**:
- Check orthonormality: $\vec{q}_i\cdot\vec{q}_j$ should equal $\delta_{ij}$. E.g., $\vec{q}_1\cdot\vec{q}_2 = \tfrac{1}{\sqrt{12}}(1-1+0)=0$. $\vec{q}_1\cdot\vec{q}_1 = \tfrac{1}{2}(1+1+0)=1$. Good.
- Check $R$ is upper-triangular with positive diagonal. Yes: $\sqrt{2},\sqrt{3/2},2/\sqrt{3}$ are all positive.
- Sanity check $A=QR$ by verifying the first column: $Q\vec{r}_1 = \sqrt{2}\cdot\vec{q}_1 = (1,1,0) = \vec{a}_1$. ✓

## 10.13 Synthesis

Q: Summarize the relationship between Gram-Schmidt, orthonormal bases, and QR.
A: Gram-Schmidt is the algorithm that turns a basis into an orthonormal basis; the resulting orthonormal vectors are the columns of $Q$; and the coefficients recorded along the way (projections and norms) populate $R$. QR decomposition is therefore just Gram-Schmidt written in matrix form.

Q: When would you prefer modified Gram-Schmidt over classical Gram-Schmidt in practice?
A: Whenever the computation is done in floating-point and the input columns are nearly linearly dependent or of very different magnitudes. Modified Gram-Schmidt preserves orthogonality of the computed $\vec{q}_k$ much better, producing a $Q$ that is closer to truly orthonormal.

Q: Why does QR decomposition make the least-squares problem both easier and more stable than the normal equations?
A: Easier because $Q^TQ=I$ reduces the normal equations to an upper-triangular system $R\vec{x}=Q^T\vec{b}$ solvable by back-substitution. More stable because we never form $A^TA$, which would square the condition number and amplify rounding error.
