+++
order = 12
subject = "Mathematics"
tags = ["math", "linear-algebra", "symmetric-matrices", "spectral-theorem", "quadratic-forms", "definiteness"]
+++

# Linear Algebra — Symmetric Matrices, Spectral Theorem, and Quadratic Forms

## 12.1 Symmetric Matrices

Q: Why single out symmetric matrices as a special class?
A: Symmetric matrices are the "best behaved" matrices for eigen-analysis: their eigenvalues are always real, their eigenvectors can always be chosen orthonormal, and they are always diagonalizable. These properties make them central to geometry (quadratic forms), statistics (covariance), and optimization (Hessians).

C: A real matrix $A$ is [symmetric] when $A^T = A$, i.e. $a_{ij} = a_{ji}$ for all entries.

C: For a symmetric matrix $A$, the entry in row $i$, column $j$ equals the entry in row $[j]$, column $[i]$.

Q: Why is every diagonal matrix symmetric?
A: If $D$ has $d_{ij} = 0$ whenever $i \neq j$, then $d_{ij} = d_{ji} = 0$ off the diagonal, so $D^T = D$. Diagonal matrices are the simplest symmetric matrices.

Q: Give three natural examples where symmetric matrices arise.
A: (1) Covariance matrices $\Sigma$ in statistics, since $\operatorname{Cov}(X_i, X_j) = \operatorname{Cov}(X_j, X_i)$. (2) Gram matrices $B^T B$ of inner products of columns of $B$. (3) Hessian matrices of second partial derivatives $\partial^2 f/\partial x_i \partial x_j$ of smooth functions, equal by Clairaut's theorem.

C: For any real matrix $B$, the Gram matrix $B^T B$ is always [symmetric], since $(B^T B)^T = B^T (B^T)^T = B^T B$.

C: The [Hessian] of a twice-continuously-differentiable function $f(\vec{x})$ is the symmetric matrix with entries $H_{ij} = \partial^2 f / \partial x_i \partial x_j$.

## 12.2 Why Symmetric Matrices Are Special

Q: What three properties make real symmetric matrices exceptional compared to general square matrices?
A: (1) All eigenvalues are real (no complex pairs). (2) Eigenvectors corresponding to distinct eigenvalues are automatically orthogonal. (3) They are always orthogonally diagonalizable: $A = PDP^T$ with $P$ orthogonal and $D$ real diagonal.

Q: What does "orthogonally diagonalizable" mean, and why is it stronger than ordinary diagonalizability?
A: Orthogonally diagonalizable means $A = PDP^T$ where $P$ is orthogonal ($P^T = P^{-1}$) and $D$ is diagonal. Ordinary diagonalization only requires $A = PDP^{-1}$ with $P$ invertible; orthogonal diagonalization additionally forces the eigenvectors (columns of $P$) to form an orthonormal basis.

C: A matrix $A$ is orthogonally diagonalizable iff there is an orthogonal matrix $P$ and diagonal $D$ with $A = P D P^{[T]}$.

## 12.3 Real Eigenvalues of Symmetric Matrices

Q: Why are eigenvalues of a real symmetric matrix always real, even though a general real matrix can have complex eigenvalues?
A: If $A\vec{v} = \lambda\vec{v}$ with $\vec{v} \neq 0$, taking conjugate transpose gives $\overline{\vec{v}}^T A = \overline{\lambda}\,\overline{\vec{v}}^T$ (using $A^T = A$ and $A$ real). Multiplying by $\vec{v}$ on the right gives $\overline{\lambda}\,\overline{\vec{v}}^T\vec{v} = \overline{\vec{v}}^T A \vec{v} = \lambda\, \overline{\vec{v}}^T\vec{v}$. Since $\overline{\vec{v}}^T\vec{v} > 0$, we get $\lambda = \overline{\lambda}$, so $\lambda$ is real.

Q: What is special about the eigenvalues of a real symmetric matrix?
A: They are all real numbers (no complex pairs).

Q: Give an example showing that a general (non-symmetric) real matrix need not have real eigenvalues.
A: The rotation matrix $\begin{pmatrix}0 & -1 \\ 1 & 0\end{pmatrix}$ has eigenvalues $\pm i$. Only special structure (like symmetry) guarantees real eigenvalues.

## 12.4 Orthogonal Eigenvectors

Q: Why are eigenvectors of a symmetric matrix for distinct eigenvalues automatically orthogonal?
A: Let $A\vec{v}_1 = \lambda_1 \vec{v}_1$ and $A\vec{v}_2 = \lambda_2\vec{v}_2$ with $\lambda_1 \neq \lambda_2$. Then $\vec{v}_1^T A \vec{v}_2 = \lambda_2 \vec{v}_1^T \vec{v}_2$. But also $\vec{v}_1^T A \vec{v}_2 = (A\vec{v}_1)^T\vec{v}_2 = \lambda_1 \vec{v}_1^T\vec{v}_2$ using $A^T = A$. Subtracting, $(\lambda_1 - \lambda_2)\vec{v}_1^T \vec{v}_2 = 0$, and since $\lambda_1 \neq \lambda_2$, we must have $\vec{v}_1^T \vec{v}_2 = 0$.

C: For a symmetric $A$ with $A\vec{v}_1 = \lambda_1 \vec{v}_1$ and $A\vec{v}_2 = \lambda_2 \vec{v}_2$, if $\lambda_1 \neq \lambda_2$ then $\vec{v}_1 \cdot \vec{v}_2 = [0]$.

Q: When a symmetric matrix has a repeated eigenvalue, how do we still obtain an orthonormal basis of eigenvectors?
A: Within the eigenspace of a repeated eigenvalue, any basis works; applying Gram-Schmidt to that basis produces an orthonormal basis of eigenvectors. Combined with orthogonality across distinct eigenvalues, this gives an orthonormal eigenbasis for all of $\mathbb{R}^n$.

## 12.5 The Spectral Theorem

Q: State the Spectral Theorem for real symmetric matrices.
A: Every real symmetric $n \times n$ matrix $A$ can be written $A = P D P^T$, where $P$ is an orthogonal matrix whose columns are an orthonormal basis of eigenvectors of $A$, and $D$ is the diagonal matrix of corresponding eigenvalues.

C: The Spectral Theorem states that for any real symmetric $A$, there exist an orthogonal $P$ and diagonal $D$ with $A = P D P^{[T]}$.

Q: Why is the Spectral Theorem called "spectral"?
A: The "spectrum" of a matrix is its set of eigenvalues. The theorem says the entire behavior of a symmetric $A$ is captured by its spectrum (the eigenvalues in $D$) together with an orthonormal eigenbasis (the columns of $P$).

Q: How does the Spectral Theorem compare to ordinary diagonalization $A = PDP^{-1}$?
A: Ordinary diagonalization holds only for diagonalizable matrices and gives an invertible but generally non-orthogonal $P$, requiring a full matrix inverse. The Spectral Theorem replaces $P^{-1}$ with the much simpler $P^T$, because the eigenvectors can be chosen orthonormal.

## 12.6 Spectral Decomposition

Q: What is the spectral decomposition of a symmetric matrix $A$?
A: Writing $A = PDP^T$ with orthonormal eigenvectors $\vec{u}_1, \ldots, \vec{u}_n$ (columns of $P$) and eigenvalues $\lambda_1, \ldots, \lambda_n$, we can expand: $A = \sum_{i=1}^n \lambda_i \vec{u}_i \vec{u}_i^T$. It expresses $A$ as a weighted sum of rank-1 projections onto each eigenvector direction.

C: The spectral decomposition of a symmetric matrix $A$ with orthonormal eigenvectors $\vec{u}_i$ and eigenvalues $\lambda_i$ is $A = \sum_{i=1}^n [\lambda_i \vec{u}_i \vec{u}_i^T]$.

Q: What does the rank-1 matrix $\vec{u}_i \vec{u}_i^T$ represent geometrically, when $\vec{u}_i$ is a unit vector?
A: It is the orthogonal projection matrix onto the 1D subspace spanned by $\vec{u}_i$. Applied to any $\vec{x}$, it gives $(\vec{u}_i^T \vec{x})\vec{u}_i$, the component of $\vec{x}$ along $\vec{u}_i$.

Q: How does the spectral decomposition let you understand $A\vec{x}$ geometrically?
A: Decompose $\vec{x} = \sum_i (\vec{u}_i^T \vec{x})\vec{u}_i$ in the eigenbasis. Then $A\vec{x} = \sum_i \lambda_i (\vec{u}_i^T \vec{x})\vec{u}_i$. So $A$ simply rescales each eigencomponent by its eigenvalue — no twisting, no shearing, just stretching along the $\vec{u}_i$ axes.

## 12.7 Procedure to Orthogonally Diagonalize

Q: What is the four-step procedure to orthogonally diagonalize a real symmetric matrix?
A: (1) Find the eigenvalues by solving $\det(A - \lambda I) = 0$. (2) For each eigenvalue, find a basis for its eigenspace by solving $(A - \lambda I)\vec{v} = 0$. (3) Apply Gram-Schmidt within each eigenspace to make those basis vectors orthogonal (eigenspaces for distinct eigenvalues are already mutually orthogonal). (4) Normalize all eigenvectors to unit length; stack them as columns of $P$, and place the eigenvalues in $D$.

Q: Why is Gram-Schmidt only applied within each eigenspace, not across eigenspaces?
A: Eigenvectors for distinct eigenvalues of a symmetric matrix are automatically orthogonal (12.4). Only within a single eigenspace (repeated eigenvalue) is there freedom to pick a basis that is not already orthogonal, so Gram-Schmidt is needed there.

C: The final step of orthogonally diagonalizing a symmetric matrix is to [normalize] each eigenvector to unit length.

## 12.8 Quadratic Forms

Q: Before reading the definition, predict: what kind of function of $(x,y)$ is $x^2 + 4xy + 3y^2$, and why might it be useful to write it using a matrix?
A: It is a homogeneous degree-2 polynomial with no linear or constant term. Writing it as $\vec{x}^T A \vec{x}$ lets us use linear-algebra tools (eigenvalues, orthogonal diagonalization) to analyze its shape, signs, and level sets.

C: A [quadratic form] on $\mathbb{R}^n$ is a function $Q(\vec{x}) = \vec{x}^T A \vec{x}$ where $A$ is a symmetric $n\times n$ matrix and $\vec{x} \in \mathbb{R}^n$.

Q: Why do we require $A$ to be symmetric in the quadratic form $Q(\vec{x}) = \vec{x}^T A \vec{x}$?
A: Any square matrix $M$ satisfies $\vec{x}^T M \vec{x} = \vec{x}^T \tfrac{M + M^T}{2} \vec{x}$, so only the symmetric part of $M$ contributes. Choosing $A$ symmetric makes the representation unique and lets us use the spectral theorem.

Q: How do you read off the symmetric matrix $A$ from a quadratic form like $Q(x,y) = x^2 + 4xy + 3y^2$?
A: The coefficient of $x_i^2$ goes on the diagonal as $a_{ii}$; the coefficient of $x_i x_j$ (with $i \neq j$) splits equally as $a_{ij} = a_{ji}$. So $A = \begin{pmatrix}1 & 2 \\ 2 & 3\end{pmatrix}$: the $1$ and $3$ are the $x^2, y^2$ coefficients, and the $4xy$ splits as $2 + 2$.

C: In the quadratic form $x^2 + 4xy + 3y^2$ written as $\vec{x}^T A \vec{x}$, the off-diagonal entries of $A$ equal half of [$4$], namely $2$.

## 12.9 Diagonalizing a Quadratic Form

Q: What does it mean to "diagonalize" a quadratic form, and why do we want to?
A: It means finding coordinates $\vec{y}$ in which $Q$ has no cross terms — only squares. In those coordinates the form is simply $\lambda_1 y_1^2 + \cdots + \lambda_n y_n^2$, which makes its sign, level sets, and critical behavior obvious.

Q: How do you diagonalize a quadratic form $Q(\vec{x}) = \vec{x}^T A \vec{x}$ using the Spectral Theorem?
A: Write $A = PDP^T$ with $P$ orthogonal, then substitute $\vec{x} = P\vec{y}$. This gives $Q = (P\vec{y})^T A (P\vec{y}) = \vec{y}^T P^T A P \vec{y} = \vec{y}^T D \vec{y} = \sum_i \lambda_i y_i^2$. The cross terms vanish.

C: Under the change of variable $\vec{x} = P\vec{y}$ with $P$ orthogonal and $A = PDP^T$, the quadratic form $\vec{x}^T A \vec{x}$ becomes $\vec{y}^T [D] \vec{y} = \sum_i \lambda_i y_i^2$.

Q: Why is it important that $P$ be orthogonal (not just invertible) when diagonalizing a quadratic form?
A: An orthogonal change of variable preserves lengths and angles — it's a rigid rotation/reflection. So the geometric shape of level sets (ellipse, hyperbola, etc.) is genuinely the same in both coordinate systems; only the axes are rotated.

## 12.10 Classification of Quadratic Forms

C: A quadratic form $Q(\vec{x}) = \vec{x}^T A \vec{x}$ is called [positive definite] if $Q(\vec{x}) > 0$ for every nonzero $\vec{x}$.

C: A quadratic form is [negative definite] if $Q(\vec{x}) < 0$ for every nonzero $\vec{x}$.

C: A quadratic form is [indefinite] if it takes both positive and negative values.

C: A quadratic form is [positive semi-definite] if $Q(\vec{x}) \geq 0$ for every $\vec{x}$ (with equality possible for some nonzero $\vec{x}$).

Q: How do you classify a quadratic form's definiteness directly from the eigenvalues of its symmetric matrix $A$?
A: Since $Q = \sum \lambda_i y_i^2$ in eigen-coordinates: positive definite iff all $\lambda_i > 0$; negative definite iff all $\lambda_i < 0$; positive semi-definite iff all $\lambda_i \geq 0$; negative semi-definite iff all $\lambda_i \leq 0$; indefinite iff $A$ has both positive and negative eigenvalues.

C: A symmetric matrix $A$ defines a positive definite quadratic form iff all its eigenvalues are [positive].

C: A symmetric matrix $A$ is indefinite iff its eigenvalues include both [positive] and [negative] values.

Q: What is the eigenvalue signature of a positive semi-definite but not positive definite matrix?
A: All eigenvalues are $\geq 0$, with at least one equal to $0$. The zero eigenvalue direction is where $Q$ vanishes without $\vec{x}$ being zero.

## 12.11 Why Definiteness Matters

Q: Why does definiteness of the Hessian matter for finding minima and maxima?
A: At a critical point of a smooth function $f$, the second-derivative test classifies it by the Hessian $H$: if $H$ is positive definite, the point is a local minimum (bowl opens upward in every direction); if negative definite, a local maximum; if indefinite, a saddle point; if semi-definite, the test is inconclusive.

C: At a critical point where the Hessian is positive definite, the function attains a local [minimum].

C: At a critical point where the Hessian is [indefinite], the function has a saddle point.

Q: Why is the covariance matrix of a random vector always positive semi-definite?
A: For any vector $\vec{a}$, the variance $\operatorname{Var}(\vec{a}^T X) = \vec{a}^T \Sigma \vec{a}$ must be $\geq 0$ since variance is nonnegative. Hence $\vec{a}^T \Sigma \vec{a} \geq 0$ for all $\vec{a}$, which is the definition of positive semi-definiteness.

## 12.12 Principal Axes Theorem

Q: What is the geometric content of the Principal Axes Theorem?
A: It says that for any quadratic form, there is a rotation of the coordinate axes — given by the orthonormal eigenvectors of $A$ — that aligns the axes with the natural symmetry directions of the level sets. In the rotated frame, the level sets become axis-aligned ellipses, hyperbolas, or parabolas (in 2D), with no mixed terms.

C: The [principal axes] of a quadratic form are the directions of the orthonormal eigenvectors of its symmetric matrix $A$.

Q: What does the level set $Q(\vec{x}) = 1$ look like when $Q$ is positive definite, and how do the eigenvalues determine its shape?
A: It is an ellipsoid centered at the origin. Along the $i$-th principal axis (eigenvector $\vec{u}_i$), the semi-axis length is $1/\sqrt{\lambda_i}$. Larger eigenvalues produce shorter axes (the form grows faster in that direction).

Q: If a symmetric $2\times 2$ matrix has eigenvalues of opposite sign, what shape are the level sets $Q(\vec{x}) = c$ for $c \neq 0$?
A: Hyperbolas, with asymptotes along the diagonals of the principal-axis frame. The indefinite signs mean $Q$ increases along one eigenvector direction and decreases along the other.

## 12.13 Rayleigh Quotient

C: The [Rayleigh quotient] of a symmetric matrix $A$ at a nonzero vector $\vec{x}$ is $R(\vec{x}) = \frac{\vec{x}^T A \vec{x}}{\vec{x}^T \vec{x}}$.

Q: What is the range of values the Rayleigh quotient $R(\vec{x})$ can take, for a symmetric matrix $A$?
A: It takes values in the interval $[\lambda_{\min}, \lambda_{\max}]$ where $\lambda_{\min}$ and $\lambda_{\max}$ are the smallest and largest eigenvalues of $A$. The minimum is attained at an eigenvector of $\lambda_{\min}$ and the maximum at an eigenvector of $\lambda_{\max}$.

Q: Why does the Rayleigh quotient reach its max at an eigenvector of the largest eigenvalue?
A: In eigen-coordinates $\vec{y} = P^T \vec{x}$, $R = \frac{\sum \lambda_i y_i^2}{\sum y_i^2}$, a weighted average of the $\lambda_i$ with weights $y_i^2 / \sum y_j^2$. A weighted average is maximized by placing all weight on the largest $\lambda_i$, i.e. choosing $\vec{y}$ (hence $\vec{x}$) along the corresponding eigenvector.

C: The maximum of the Rayleigh quotient of a symmetric matrix $A$ equals its [largest eigenvalue].

## 12.14 Constrained Optimization on the Unit Sphere

Q: How does the Rayleigh quotient solve the constrained problem "maximize $\vec{x}^T A \vec{x}$ subject to $\|\vec{x}\| = 1$"?
A: On the unit sphere $\vec{x}^T \vec{x} = 1$, the quadratic form equals the Rayleigh quotient: $\vec{x}^T A \vec{x} = R(\vec{x})$. So the constrained maximum is $\lambda_{\max}$, attained at a unit eigenvector of $\lambda_{\max}$. The minimum is $\lambda_{\min}$, attained at a unit eigenvector of $\lambda_{\min}$.

C: The maximum of $\vec{x}^T A \vec{x}$ over unit vectors $\vec{x}$ equals the [largest eigenvalue] of the symmetric matrix $A$.

Q: Why does this constrained optimization result matter in practice (e.g. in PCA)?
A: In Principal Component Analysis, the first principal direction is the unit vector $\vec{u}$ maximizing variance $\vec{u}^T \Sigma \vec{u}$ of projected data. By this theorem, $\vec{u}$ is the top eigenvector of the covariance matrix $\Sigma$, and the maximum variance equals the largest eigenvalue.

## 12.15 Procedure: Orthogonally Diagonalize and Classify

P: Orthogonally diagonalize the symmetric matrix $A = \begin{pmatrix}2 & 1 \\ 1 & 2\end{pmatrix}$ and classify the associated quadratic form $Q(x,y) = 2x^2 + 2xy + 2y^2$.

S:
**IDENTIFY**: This is a spectral-theorem problem for a $2\times 2$ symmetric matrix. We need to (a) find eigenvalues, (b) find orthonormal eigenvectors, (c) build $P$ and $D$ so that $A = PDP^T$, and (d) classify the form by the signs of the eigenvalues.

**PLAN**:
- Solve $\det(A - \lambda I) = 0$ for eigenvalues $\lambda_1, \lambda_2$.
- For each $\lambda_i$, solve $(A - \lambda_i I)\vec{v} = 0$ for an eigenvector.
- Normalize each eigenvector (they are already orthogonal since eigenvalues differ).
- Assemble $P = [\vec{u}_1\ \vec{u}_2]$ and $D = \operatorname{diag}(\lambda_1, \lambda_2)$.
- Inspect signs of $\lambda_1, \lambda_2$ to classify $Q$.

**EXECUTE**:
1. Characteristic polynomial: $\det\begin{pmatrix}2-\lambda & 1 \\ 1 & 2-\lambda\end{pmatrix} = (2-\lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = (\lambda-1)(\lambda-3)$. So $\lambda_1 = 1,\ \lambda_2 = 3$.
2. For $\lambda_1 = 1$: $(A - I)\vec{v} = \begin{pmatrix}1 & 1 \\ 1 & 1\end{pmatrix}\vec{v} = 0$ gives $\vec{v}_1 = (1,-1)$.
3. For $\lambda_2 = 3$: $(A - 3I)\vec{v} = \begin{pmatrix}-1 & 1 \\ 1 & -1\end{pmatrix}\vec{v} = 0$ gives $\vec{v}_2 = (1,1)$.
4. Normalize: $\vec{u}_1 = \tfrac{1}{\sqrt{2}}(1,-1)$, $\vec{u}_2 = \tfrac{1}{\sqrt{2}}(1,1)$. Check orthogonality: $\vec{u}_1 \cdot \vec{u}_2 = \tfrac{1}{2}(1 - 1) = 0$. ✓
5. Assemble: $P = \tfrac{1}{\sqrt{2}}\begin{pmatrix}1 & 1 \\ -1 & 1\end{pmatrix}$, $D = \begin{pmatrix}1 & 0 \\ 0 & 3\end{pmatrix}$, and $A = PDP^T$.
6. Classify: both eigenvalues $1, 3$ are positive, so $Q$ is positive definite.

**EVALUATE**:
- Sanity check: $\operatorname{tr}(A) = 4 = \lambda_1 + \lambda_2 = 1 + 3$ ✓ and $\det(A) = 3 = \lambda_1 \lambda_2$ ✓.
- In the new coordinates $\vec{y} = P^T \vec{x}$, $Q = y_1^2 + 3 y_2^2 > 0$ for $\vec{y}\neq 0$, confirming positive definiteness.
- Level set $Q = 1$ is an ellipse with semi-axes $1/\sqrt{1} = 1$ along $\vec{u}_1$ and $1/\sqrt{3}$ along $\vec{u}_2$ — rotated $45°$ from the standard axes, as expected for a symmetric off-diagonal coupling.
