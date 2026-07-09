+++
order = 13
subject = "Mathematics"
tags = ["math", "linear-algebra", "svd", "singular-values", "pseudoinverse", "low-rank-approximation", "pca"]
+++

# Linear Algebra — Singular Value Decomposition

## 13.1 Why SVD

Q: Before diving into SVD, predict: what limitation of eigendecomposition $A = PDP^{-1}$ might SVD overcome?
A: Eigendecomposition requires $A$ to be square and diagonalizable. Many real matrices are neither — data matrices are usually rectangular ($m \neq n$), and even square matrices may fail to be diagonalizable. SVD should work for any matrix to be genuinely useful.

Q: Why is SVD often called the "universal" matrix factorization?
A: Because every real $m \times n$ matrix $A$ admits an SVD — no assumptions about shape, rank, or diagonalizability are needed. In contrast, eigendecomposition requires $A$ to be square and have a full set of linearly independent eigenvectors. SVD therefore applies in settings where eigendecomposition silently fails.

C: Unlike eigendecomposition, SVD exists for [every real $m \times n$ matrix], with no requirement that the matrix be square or diagonalizable.

Q: Why is SVD especially valuable for data analysis where matrices are typically rectangular?
A: Data matrices usually have rows = observations and columns = features, so $m \neq n$. Eigendecomposition cannot be applied to such matrices at all, but SVD extracts a meaningful set of axes (singular vectors) and magnitudes (singular values) regardless of shape, making it the natural tool for dimensionality reduction and compression.

## 13.2 Singular Values

Q: How are the singular values $\sigma_i$ of an $m \times n$ matrix $A$ defined?
A: $\sigma_i = \sqrt{\lambda_i(A^T A)}$, the square root of the $i$-th eigenvalue of $A^T A$.

C: Singular values are always [nonnegative], because they are square roots of eigenvalues of the positive semi-definite matrix $A^T A$.

C: By convention, singular values are ordered so that $\sigma_1 \geq \sigma_2 \geq \cdots \geq [\sigma_{\min(m,n)}] \geq 0$.

Q: Why are singular values guaranteed to be real and nonnegative, even when $A$ has no real eigenvalues?
A: Singular values come from eigenvalues of $A^T A$, which is symmetric positive semi-definite. By the spectral theorem, symmetric matrices have real eigenvalues, and positive semi-definiteness guarantees those eigenvalues are $\geq 0$. Taking square roots therefore yields real, nonnegative numbers — regardless of what $A$ itself looks like.

## 13.3 Why $A^TA$ Is the Right Object

Q: Why does SVD build on $A^T A$ rather than $A$ itself?
A: $A^T A$ is always symmetric, because $(A^T A)^T = A^T A$. This means the spectral theorem applies: $A^T A$ has real eigenvalues and an orthonormal basis of eigenvectors. Since $A$ itself is generally non-square and non-symmetric, neither of these properties holds for $A$ alone.

C: For any matrix $A$, the product $A^T A$ is always [symmetric positive semi-definite], giving it real nonnegative eigenvalues and an orthonormal eigenbasis.

Q: Why is $A^T A$ positive semi-definite for every matrix $A$?
A: For any vector $\vec{x}$, $\vec{x}^T (A^T A) \vec{x} = (A\vec{x})^T(A\vec{x}) = \|A\vec{x}\|^2 \geq 0$. Since the quadratic form is nonnegative for every $\vec{x}$, $A^T A$ is positive semi-definite by definition.

C: Applying the [spectral theorem] to $A^T A$ yields an orthonormal basis of eigenvectors — these become the right singular vectors of $A$.

## 13.4 The SVD Theorem

C: The SVD theorem states that every $m \times n$ matrix $A$ can be factored as $A = [U \Sigma V^T]$, where $U$ is $m \times m$ orthogonal, $V$ is $n \times n$ orthogonal, and $\Sigma$ is $m \times n$ diagonal.

C: In the SVD $A = U \Sigma V^T$, the matrix $\Sigma$ has the singular values on its diagonal and [zeros] elsewhere; it has the same shape as $A$.

Q: In the SVD $A = U \Sigma V^T$, what are the sizes of $U$, $\Sigma$, and $V$ for an $m \times n$ matrix $A$?
A: $U$ is $m \times m$, $V$ is $n \times n$, and $\Sigma$ is $m \times n$ (same shape as $A$). The orthogonal matrices are always square; only $\Sigma$ inherits the rectangular shape of $A$.

Q: What does it mean that $U$ and $V$ are "orthogonal" matrices in the SVD?
A: Orthogonal means $U^T U = I_m$ and $V^T V = I_n$, i.e. their columns form orthonormal bases of $\mathbb{R}^m$ and $\mathbb{R}^n$ respectively. Equivalently, $U^{-1} = U^T$ and $V^{-1} = V^T$, which makes the decomposition numerically stable and geometrically a rotation/reflection.

C: The diagonal entries of $\Sigma$ in the SVD are the [singular values] $\sigma_1 \geq \sigma_2 \geq \cdots \geq 0$ of $A$.

## 13.5 Right Singular Vectors

C: The columns of $V$ in the SVD $A = U \Sigma V^T$ are the [orthonormal eigenvectors of $A^T A$]; they are called the right singular vectors of $A$.

Q: Why are the right singular vectors defined as eigenvectors of $A^T A$?
A: If $A = U \Sigma V^T$, then $A^T A = V \Sigma^T U^T U \Sigma V^T = V (\Sigma^T \Sigma) V^T$. This is an eigendecomposition of $A^T A$ with eigenvectors equal to columns of $V$ and eigenvalues equal to $\sigma_i^2$. So $V$'s columns must be the orthonormal eigenvectors of $A^T A$.

C: If $\vec{v}_i$ is the $i$-th column of $V$, then $A^T A \vec{v}_i = [\sigma_i^2] \vec{v}_i$.

## 13.6 Left Singular Vectors

C: The columns of $U$ in the SVD $A = U \Sigma V^T$ are the [orthonormal eigenvectors of $A A^T$]; they are called the left singular vectors of $A$.

Q: Given the right singular vector $\vec{v}_i$ and a nonzero singular value $\sigma_i$, how do you compute the left singular vector $\vec{u}_i$?
A: Using the relation $\vec{u}_i = \dfrac{A \vec{v}_i}{\sigma_i}$, where $\vec{v}_i$ is the $i$-th column of $V$ and $\sigma_i$ is the $i$-th singular value. This formula is valid whenever $\sigma_i \neq 0$; the remaining $\vec{u}_i$ (for zero singular values) are chosen to complete an orthonormal basis of $\mathbb{R}^m$.

Q: Why does $\vec{u}_i = A\vec{v}_i / \sigma_i$ give a unit vector?
A: Because $\|A \vec{v}_i\|^2 = \vec{v}_i^T A^T A \vec{v}_i = \vec{v}_i^T (\sigma_i^2 \vec{v}_i) = \sigma_i^2$, so $\|A \vec{v}_i\| = \sigma_i$. Dividing by $\sigma_i$ normalizes the vector to unit length.

C: The key identity linking singular vectors is $A \vec{v}_i = [\sigma_i \vec{u}_i]$, valid for every $i$ including $\sigma_i = 0$.

## 13.7 Geometric Interpretation

Q: Geometrically, what does a matrix $A$ do to the unit sphere in $\mathbb{R}^n$?
A: $A$ maps the unit sphere $\{\vec{x} \in \mathbb{R}^n : \|\vec{x}\| = 1\}$ to an ellipsoid in $\mathbb{R}^m$ (or a degenerate lower-dimensional version if $A$ is not full rank). The SVD reveals the axes of this ellipsoid explicitly.

C: In the geometric view of SVD, the singular values $\sigma_i$ are the [semi-axis lengths] of the ellipsoid image of the unit sphere under $A$.

C: In the geometric view of SVD, the left singular vectors $\vec{u}_i$ are the [directions of the semi-axes] of the ellipsoid image of the unit sphere under $A$.

Q: What does the decomposition $A = U \Sigma V^T$ mean as a sequence of three geometric operations?
A: Reading right-to-left: $V^T$ rotates/reflects input to align with the principal input directions; $\Sigma$ stretches each axis by $\sigma_i$ (and possibly changes dimension by padding with zeros); $U$ rotates/reflects into the output space. So every linear map is "rotation, axis-aligned scaling, rotation."

## 13.8 Rank From SVD

C: The rank of $A$ equals the number of [nonzero singular values] in its SVD.

Q: Why does the number of nonzero singular values equal the rank of $A$?
A: Rank equals the dimension of $\text{Col}(A)$. From $A = U \Sigma V^T$, a column $A\vec{v}_i = \sigma_i \vec{u}_i$ is nonzero iff $\sigma_i \neq 0$. The nonzero $\vec{u}_i$ are orthonormal and span $\text{Col}(A)$, so their count — the number of nonzero $\sigma_i$ — is the rank.

## 13.9 Fundamental Subspaces From SVD

Let $A$ have rank $r$ with SVD $A = U \Sigma V^T$.

C: The column space $\text{Col}(A)$ is spanned by the [first $r$ columns of $U$] (the left singular vectors with nonzero singular values).

C: The null space $\text{Nul}(A)$ is spanned by the [last $n - r$ columns of $V$] (the right singular vectors with zero singular values).

C: The row space $\text{Row}(A)$ is spanned by the [first $r$ columns of $V$] (the right singular vectors with nonzero singular values).

C: The left null space $\text{Nul}(A^T)$ is spanned by the [last $m - r$ columns of $U$] (the left singular vectors with zero singular values).

Q: Why does SVD give orthonormal bases for all four fundamental subspaces of $A$ simultaneously?
A: Because $U$ partitions $\mathbb{R}^m$ into $\text{Col}(A) \oplus \text{Nul}(A^T)$ and $V$ partitions $\mathbb{R}^n$ into $\text{Row}(A) \oplus \text{Nul}(A)$, with the split happening exactly at the index $r$ where singular values become zero. No other decomposition reveals all four subspaces at once with orthonormal bases.

## 13.10 Reduced (Thin) SVD

C: The reduced (thin) SVD of a rank-$r$ matrix $A$ is $A = [U_r \Sigma_r V_r^T]$, using only the first $r$ columns of $U$, the top-left $r \times r$ block of $\Sigma$, and the first $r$ columns of $V$.

Q: Why is the reduced SVD often preferred in practice over the full SVD?
A: The zero singular values contribute nothing to $A$, so the columns of $U$ and $V$ they multiply are extraneous. The reduced form drops them, storing $O(r(m+n))$ numbers instead of $O(m^2 + n^2 + mn)$. This is a huge savings when $r \ll \min(m, n)$, as in most real data.

C: In the reduced SVD $A = U_r \Sigma_r V_r^T$, the matrix $\Sigma_r$ is [$r \times r$] diagonal with strictly positive entries $\sigma_1, \ldots, \sigma_r$.

## 13.11 Outer-Product Form

C: The outer-product form of SVD writes $A = \sum_{i=1}^r [\sigma_i \vec{u}_i \vec{v}_i^T]$, where $\vec{u}_i \vec{v}_i^T$ is a rank-1 matrix of size $m \times n$.

Q: Why does $\vec{u}_i \vec{v}_i^T$ have rank 1, and what is its shape?
A: It is the outer product of an $m$-vector and an $n$-vector, giving an $m \times n$ matrix whose columns are all scalar multiples of $\vec{u}_i$. A matrix with all columns proportional has a 1-dimensional column space, i.e. rank 1.

Q: What is the intuition behind writing $A$ as $\sum \sigma_i \vec{u}_i \vec{v}_i^T$?
A: It decomposes $A$ into a sum of rank-1 "ingredients," each with strength $\sigma_i$. Because singular values are ordered, earlier terms contribute more than later terms, so the sum reveals which rank-1 components matter most. This is the foundation of low-rank approximation.

## 13.12 Low-Rank Approximation (Eckart–Young)

Q: Before stating the Eckart–Young theorem, predict: if you wanted the best rank-$k$ approximation of $A$, which terms of the outer-product SVD would you keep?
A: The terms with the largest singular values — i.e. the first $k$ terms. They carry the most "energy," so truncating after them should minimize the approximation error.

C: The Eckart–Young theorem states that the best rank-$k$ approximation of $A$ (in Frobenius or spectral norm) is $A_k = \sum_{i=1}^{k} [\sigma_i \vec{u}_i \vec{v}_i^T]$, obtained by truncating the SVD after $k$ terms.

Q: What does "best" mean in the Eckart–Young theorem for low-rank approximation?
A: It means that among all matrices $B$ of rank at most $k$, $A_k$ minimizes both $\|A - B\|_F$ (Frobenius norm) and $\|A - B\|_2$ (spectral norm). No other rank-$k$ matrix approximates $A$ more accurately in these norms.

C: The Frobenius-norm error of the best rank-$k$ SVD approximation is $\|A - A_k\|_F = \sqrt{[\sum_{i=k+1}^r \sigma_i^2]}$, the root-sum-square of the discarded singular values.

Q: How does Eckart–Young explain the intuition of SVD-based image compression?
A: An image is a matrix of pixel values. Its SVD gives a series of rank-1 pieces ordered by importance. Keeping only the top $k$ singular components reconstructs the image using much less storage; Eckart–Young guarantees this is the best possible rank-$k$ approximation. Small $\sigma_i$ correspond to fine detail/noise we can discard with minimal perceptual loss.

## 13.13 The Pseudoinverse

Q: Why do we need a generalization of the matrix inverse?
A: The inverse $A^{-1}$ exists only for square, nonsingular matrices. For rectangular or rank-deficient matrices — including almost all data matrices — we still want a "best" tool to invert $A\vec{x} = \vec{b}$. The Moore–Penrose pseudoinverse $A^+$ fills this role using SVD.

C: The Moore–Penrose pseudoinverse is $A^+ = [V \Sigma^+ U^T]$, where $\Sigma^+$ is obtained from $\Sigma$ by transposing and replacing each nonzero singular value $\sigma_i$ with $1/\sigma_i$ (zeros stay zero).

C: For an invertible square matrix, the pseudoinverse $A^+$ coincides with the ordinary inverse $[A^{-1}]$.

Q: What problem does $\vec{x} = A^+ \vec{b}$ solve when $A\vec{x} = \vec{b}$ has no exact solution or infinitely many solutions?
A: It returns the minimum-norm least-squares solution: the vector $\vec{x}$ that minimizes $\|A\vec{x} - \vec{b}\|$, and among all such minimizers, has the smallest $\|\vec{x}\|$. This makes $A^+$ the unique "best" answer in both over- and under-determined systems.

Q: Why can't we just invert singular values that are zero when building $\Sigma^+$?
A: $1/0$ is undefined, and more importantly, a zero singular value means $A$ annihilates its corresponding direction — there is no way to recover information lost in that direction. Leaving the entry at zero in $\Sigma^+$ is the mathematically correct choice: the pseudoinverse does nothing along directions $A$ destroys.

## 13.14 Condition Number

C: The condition number of a rank-$r$ matrix $A$ is $\kappa(A) = [\sigma_1 / \sigma_r]$, the ratio of its largest to smallest nonzero singular value.

Q: Why does a large condition number signal numerical instability?
A: $\kappa(A)$ measures how much input error can be amplified in $A\vec{x} = \vec{b}$. If $\sigma_r$ is tiny compared to $\sigma_1$, the matrix stretches some directions much more than it shrinks others, so tiny perturbations in $\vec{b}$ produce huge changes in $\vec{x}$. Well-conditioned matrices have $\kappa \approx 1$; ill-conditioned ones have $\kappa \gg 1$.

Q: When is a matrix called "singular" or "ill-conditioned" in terms of its singular values?
A: A matrix is singular when it has at least one zero singular value ($\sigma_r = 0$), making $\kappa(A) = \infty$. It is ill-conditioned when its smallest nonzero singular value is very close to zero relative to $\sigma_1$, giving a large but finite $\kappa(A)$.

## 13.15 Applications

Q: How is SVD used in Principal Component Analysis (PCA)?
A: After mean-centering a data matrix $X$ (rows = observations), the right singular vectors $\vec{v}_i$ are the principal component directions and the singular values $\sigma_i$ measure the variance captured along each direction. PCA is essentially SVD of the centered data matrix, projecting data onto the top-$k$ singular directions.

Q: How does SVD enable image compression?
A: Treating the image as a matrix, replacing it by its rank-$k$ SVD approximation $A_k = \sum_{i=1}^k \sigma_i \vec{u}_i \vec{v}_i^T$ stores only $k(m + n + 1)$ numbers instead of $mn$. Because Eckart–Young guarantees $A_k$ is optimal, visually significant features survive while fine noise is discarded.

Q: How do recommender systems use SVD?
A: A user–item ratings matrix is typically huge, sparse, and low-rank in latent structure (tastes cluster). SVD (or its variants) factors it into user and item feature matrices via low-rank approximation, letting the system fill in missing ratings by reconstructing entries from the dominant singular components.

C: In dimensionality reduction, projecting data onto the top-$k$ right singular vectors gives the best $k$-dimensional linear approximation, a direct consequence of the [Eckart–Young theorem].

## 13.16 SVD vs Eigendecomposition

Q: What are the three key advantages of SVD over eigendecomposition for a general matrix?
A: First, SVD exists for every matrix, while eigendecomposition requires square, diagonalizable matrices. Second, SVD produces real, nonnegative singular values even when eigenvalues are complex. Third, SVD's singular vectors are automatically orthonormal, while general eigenvectors need not be orthogonal.

Q: When do SVD and eigendecomposition coincide?
A: When $A$ is symmetric positive semi-definite. Then $A = PDP^T$ from the spectral theorem is already an SVD: take $U = V = P$ and $\Sigma = D$. The eigenvalues equal the singular values in this case.

Q: For a symmetric but indefinite matrix $A$ (with some negative eigenvalues), how do eigendecomposition and SVD differ?
A: Eigendecomposition gives $A = PDP^T$ with possibly negative entries in $D$. SVD gives $A = U \Sigma V^T$ with nonnegative $\Sigma$; the sign changes get absorbed into differences between $U$ and $V$ (specifically, $\vec{u}_i = \pm \vec{v}_i$ depending on the sign of each eigenvalue). So $\sigma_i = |\lambda_i|$.

C: Singular vectors are always [orthonormal], whereas eigenvectors of a general matrix need not be orthogonal or even linearly independent.

## 13.17 Worked Example: Full SVD of a $2 \times 3$ Matrix

P: Compute the full SVD $A = U \Sigma V^T$ of
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix},$$
a $2 \times 3$ matrix. Find $V$, $\Sigma$, and $U$ explicitly, then verify the factorization.

S:
**IDENTIFY**: Compute a full SVD of a non-square matrix. Need right singular vectors (eigenvectors of $A^T A$), singular values ($\sqrt{\text{eigenvalues}}$), and left singular vectors ($A\vec{v}_i/\sigma_i$).

**PLAN**:
- Step 1: form $A^T A$ (a $3 \times 3$ symmetric matrix) and find its eigenvalues/eigenvectors.
- Step 2: sort eigenvalues in decreasing order; take square roots to get $\sigma_1, \sigma_2, \sigma_3$.
- Step 3: normalize eigenvectors to build $V$ ($3 \times 3$ orthogonal).
- Step 4: for each nonzero $\sigma_i$, compute $\vec{u}_i = A\vec{v}_i/\sigma_i$; complete $U$ to a $2 \times 2$ orthonormal basis if needed.
- Step 5: assemble $\Sigma$ as the $2 \times 3$ diagonal matrix with singular values; verify $A = U \Sigma V^T$.

**EXECUTE**:

Step 1. Compute $A^T A$:
$$A^T A = \begin{pmatrix} 1 & 0 \\ 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 1 & 0 \\ 1 & 2 & 1 \\ 0 & 1 & 1 \end{pmatrix}.$$

Find eigenvalues of $A^T A$ from $\det(A^T A - \lambda I) = 0$. Expanding:
$$-\lambda^3 + 4\lambda^2 - 3\lambda = -\lambda(\lambda - 1)(\lambda - 3) = 0,$$
so eigenvalues are $\lambda_1 = 3,\ \lambda_2 = 1,\ \lambda_3 = 0$.

Step 2. Singular values: $\sigma_1 = \sqrt{3},\ \sigma_2 = 1,\ \sigma_3 = 0$. So rank $r = 2$.

Step 3. Eigenvectors of $A^T A$:
- For $\lambda = 3$: solve $(A^T A - 3I)\vec{v} = 0$. Unnormalized $\vec{v}_1 = (1, 2, 1)$; normalized $\vec{v}_1 = \frac{1}{\sqrt{6}}(1, 2, 1)$.
- For $\lambda = 1$: unnormalized $\vec{v}_2 = (1, 0, -1)$; normalized $\vec{v}_2 = \frac{1}{\sqrt{2}}(1, 0, -1)$.
- For $\lambda = 0$: unnormalized $\vec{v}_3 = (1, -1, 1)$; normalized $\vec{v}_3 = \frac{1}{\sqrt{3}}(1, -1, 1)$.

Then
$$V = \begin{pmatrix} 1/\sqrt{6} & 1/\sqrt{2} & 1/\sqrt{3} \\ 2/\sqrt{6} & 0 & -1/\sqrt{3} \\ 1/\sqrt{6} & -1/\sqrt{2} & 1/\sqrt{3} \end{pmatrix}.$$

Step 4. Left singular vectors from $\vec{u}_i = A\vec{v}_i/\sigma_i$:
- $A\vec{v}_1 = \frac{1}{\sqrt{6}}(1+2,\ 2+1) = \frac{1}{\sqrt{6}}(3, 3)$. Divide by $\sigma_1 = \sqrt{3}$: $\vec{u}_1 = \frac{3}{\sqrt{18}}(1,1) = \frac{1}{\sqrt{2}}(1, 1)$.
- $A\vec{v}_2 = \frac{1}{\sqrt{2}}(1+0,\ 0-1) = \frac{1}{\sqrt{2}}(1, -1)$. Divide by $\sigma_2 = 1$: $\vec{u}_2 = \frac{1}{\sqrt{2}}(1, -1)$.

Since $m = 2$, these two already form an orthonormal basis of $\mathbb{R}^2$, so
$$U = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}.$$

Step 5. Assemble
$$\Sigma = \begin{pmatrix} \sqrt{3} & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}.$$

**EVALUATE**:
- Check shapes: $U$ is $2 \times 2$, $\Sigma$ is $2 \times 3$, $V^T$ is $3 \times 3$ — product is $2 \times 3$, matching $A$. ✓
- Check orthogonality: $U^T U = I_2$ and $V^T V = I_3$ by construction. ✓
- Check rank: two nonzero singular values match $\operatorname{rank}(A) = 2$. ✓
- Spot-check the product: the $(1,1)$ entry of $U \Sigma V^T$ is $\tfrac{1}{\sqrt{2}}\cdot \sqrt{3}\cdot \tfrac{1}{\sqrt{6}} + \tfrac{1}{\sqrt{2}} \cdot 1 \cdot \tfrac{1}{\sqrt{2}} = \tfrac{1}{2} + \tfrac{1}{2} = 1$, matching $A_{11} = 1$. ✓
- Fundamental subspaces: $\text{Nul}(A)$ is spanned by $\vec{v}_3 = \frac{1}{\sqrt{3}}(1,-1,1)$; indeed $A(1,-1,1)^T = (0,0)^T$. ✓
