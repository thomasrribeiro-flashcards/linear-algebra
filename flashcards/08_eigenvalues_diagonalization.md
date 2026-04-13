+++
order = 8
tags = ["math", "linear-algebra", "eigenvalues", "eigenvectors", "diagonalization", "characteristic-polynomial"]
+++

# Linear Algebra — Eigenvalues, Eigenvectors, and Diagonalization

## 8.1 Eigenvalue and Eigenvector Definition

Q: Why are eigenvectors of $A$ special among all vectors?
A: Multiplying by $A$ usually rotates and rescales a vector, changing its direction. An eigenvector is a nonzero vector whose direction is unchanged by $A$ — the action of $A$ on it reduces to pure scaling by a single number. This makes eigenvectors the natural "axes" along which $A$ acts most simply.

C: A nonzero vector $\vec{v}$ is an [eigenvector] of $A$ if $A\vec{v} = \lambda\vec{v}$ for some scalar $\lambda$, where $A$ is an $n\times n$ matrix and $\vec{v}\in\mathbb{R}^n$.

C: In the equation $A\vec{v} = \lambda\vec{v}$, the scalar $\lambda$ is called the [eigenvalue] associated with the eigenvector $\vec{v}$.

Q: Why must an eigenvector $\vec{v}$ be required to be nonzero?
A: The equation $A\vec{0} = \lambda\vec{0}$ holds trivially for every scalar $\lambda$, so $\vec{0}$ would be an "eigenvector" for every number. Excluding it makes eigenvalues meaningful: each eigenvalue is tied to a genuine fixed direction.

Q: Can an eigenvalue $\lambda$ equal zero?
A: Yes. $\lambda = 0$ is an eigenvalue of $A$ exactly when there is a nonzero $\vec{v}$ with $A\vec{v}=\vec{0}$, i.e., when $A$ is not invertible. The corresponding eigenvectors are the nonzero vectors in $\text{Nul}(A)$.

C: $\lambda = 0$ is an eigenvalue of $A$ if and only if $A$ is [not invertible] (equivalently, $\det A = 0$).

## 8.2 Why Eigenvectors Matter

Q: Why do eigenvectors matter for understanding a linear map?
A: Along an eigenvector direction, the matrix acts like simple multiplication by a number. If we can find enough eigenvectors to form a basis, the entire action of $A$ decouples into independent one-dimensional scalings — turning a complicated coupled transformation into $n$ separate easy ones.

Q: Why do eigenvectors make iterated dynamics $\vec{x}_{k+1}=A\vec{x}_k$ tractable?
A: Along an eigenvector, $A^k\vec{v} = \lambda^k\vec{v}$, so iteration reduces to scalar powers. Decomposing $\vec{x}_0$ in an eigenvector basis turns the dynamics into independent geometric sequences, one per eigenvalue.

Q: What does it mean intuitively to "diagonalize" a matrix?
A: It means finding a basis in which $A$ acts as pure axis-aligned scaling. In that basis the matrix is diagonal, so every operation (powers, solving systems, exponentiating) becomes trivial componentwise.

## 8.3 Eigenspaces

C: The [eigenspace] of $A$ corresponding to eigenvalue $\lambda$ is $E_\lambda = \text{Nul}(A - \lambda I)$, where $I$ is the $n\times n$ identity matrix.

Q: Why is the eigenspace $E_\lambda$ always a subspace of $\mathbb{R}^n$?
A: It is defined as the null space of the matrix $A - \lambda I$, and null spaces are always subspaces. Concretely, sums and scalar multiples of vectors satisfying $A\vec{v}=\lambda\vec{v}$ also satisfy that equation.

Q: What does $E_\lambda$ contain besides the eigenvectors for $\lambda$?
A: It contains all eigenvectors for $\lambda$ together with the zero vector. The zero vector is in every null space but is excluded from the eigenvector definition; the eigenspace is the full subspace.

C: The nonzero vectors of $E_\lambda$ are exactly the [eigenvectors] of $A$ associated with eigenvalue $\lambda$.

## 8.4 Finding Eigenvalues — Characteristic Equation

Q: Why does $A\vec{v}=\lambda\vec{v}$ lead to $\det(A-\lambda I)=0$?
A: Rewrite as $(A-\lambda I)\vec{v}=\vec{0}$. A nonzero solution $\vec{v}$ exists iff $A-\lambda I$ is singular, which is equivalent to $\det(A-\lambda I)=0$. So eigenvalues are exactly the scalars making this determinant vanish.

C: The [characteristic equation] of $A$ is $\det(A - \lambda I) = 0$, whose roots are the eigenvalues of $A$.

Q: Why is requiring $\vec{v}\neq\vec{0}$ what forces $A-\lambda I$ to be singular?
A: If $A-\lambda I$ were invertible, the only solution of $(A-\lambda I)\vec{v}=\vec{0}$ would be $\vec{v}=\vec{0}$. A nonzero eigenvector therefore requires the matrix to have nontrivial null space, i.e., zero determinant.

## 8.5 The Characteristic Polynomial

C: The [characteristic polynomial] of an $n\times n$ matrix $A$ is $p(\lambda) = \det(A - \lambda I)$, a polynomial of degree $n$ in $\lambda$.

Q: Why is $p(\lambda)=\det(A-\lambda I)$ a polynomial of degree exactly $n$?
A: The determinant is a sum over permutations of products of entries of $A-\lambda I$. The only way to get the highest power is the diagonal product $(a_{11}-\lambda)\cdots(a_{nn}-\lambda)$, giving leading term $(-\lambda)^n$. All other terms have strictly lower degree.

C: The eigenvalues of $A$ are precisely the [roots] of its characteristic polynomial $p(\lambda)=\det(A-\lambda I)$.

Q: Why can an $n\times n$ real matrix have at most $n$ distinct eigenvalues?
A: Its characteristic polynomial has degree $n$, and a degree-$n$ polynomial has at most $n$ roots in any field. Counting multiplicities, it has exactly $n$ roots over $\mathbb{C}$.

## 8.6 Finding Eigenvectors

Q: Once you know an eigenvalue $\lambda$, how do you find its eigenvectors?
A: Form $A-\lambda I$ and solve the homogeneous system $(A-\lambda I)\vec{v}=\vec{0}$ by row reduction. The nonzero vectors in the resulting null space are the eigenvectors for $\lambda$, and a basis for that null space spans $E_\lambda$.

C: To find eigenvectors for eigenvalue $\lambda$, solve the homogeneous system $[(A - \lambda I)\vec{v} = \vec{0}]$, where $\vec{v}\in\mathbb{R}^n$.

Q: Why is every eigenspace at least 1-dimensional?
A: Because $\lambda$ is an eigenvalue only when $A-\lambda I$ is singular, so its null space is nontrivial. That null space is $E_\lambda$, hence $\dim E_\lambda \geq 1$.

## 8.7 Triangular Matrices

C: The eigenvalues of a triangular matrix are its [diagonal entries].

Q: Why are the eigenvalues of a triangular matrix its diagonal entries?
A: For triangular $A$, the matrix $A-\lambda I$ is also triangular, and the determinant of a triangular matrix is the product of its diagonal entries. So $\det(A-\lambda I)=\prod_i (a_{ii}-\lambda)$, whose roots are exactly the $a_{ii}$.

## 8.8 Eigenvalues of $A^T$

C: The matrix $A$ and its transpose $A^T$ have the [same eigenvalues] (with the same algebraic multiplicities).

Q: Why do $A$ and $A^T$ share eigenvalues?
A: Because $\det(A^T - \lambda I) = \det((A-\lambda I)^T) = \det(A - \lambda I)$, since transposing does not change the determinant. Therefore $A$ and $A^T$ have the same characteristic polynomial and hence the same eigenvalues.

Q: Do $A$ and $A^T$ have the same eigenvectors?
A: Generally no. They share eigenvalues but typically have different eigenspaces; the eigenvectors of $A^T$ are called the left eigenvectors of $A$.

## 8.9 Eigenvalues of Matrix Powers

C: If $A\vec{v} = \lambda\vec{v}$ with $\vec{v}\neq\vec{0}$, then $A^k\vec{v} = [\lambda^k]\vec{v}$ for every positive integer $k$.

Q: Why is $\lambda^k$ an eigenvalue of $A^k$ whenever $\lambda$ is an eigenvalue of $A$?
A: Apply $A$ repeatedly to an eigenvector: $A^2\vec{v}=A(\lambda\vec{v})=\lambda(A\vec{v})=\lambda^2\vec{v}$, and inductively $A^k\vec{v}=\lambda^k\vec{v}$. Since $\vec{v}\neq\vec{0}$, this shows $\lambda^k$ is an eigenvalue of $A^k$ with the same eigenvector.

Q: If $A$ is invertible with eigenvalue $\lambda$, what is the corresponding eigenvalue of $A^{-1}$?
A: It is $\lambda^{-1}$. From $A\vec{v}=\lambda\vec{v}$ with $\lambda\neq 0$ (invertibility forces this), multiply both sides by $A^{-1}/\lambda$ to get $A^{-1}\vec{v}=\lambda^{-1}\vec{v}$.

## 8.10 Trace and Determinant via Eigenvalues

C: The sum of the eigenvalues of $A$ (counted with algebraic multiplicity) equals $[\text{trace}(A)]$, the sum of the diagonal entries of $A$.

C: The product of the eigenvalues of $A$ (counted with algebraic multiplicity) equals $[\det(A)]$.

Q: Why does $\det A = \prod_i \lambda_i$?
A: Over $\mathbb{C}$, the characteristic polynomial factors as $p(\lambda)=\prod_i(\lambda_i-\lambda)$. Evaluating at $\lambda=0$ gives $p(0)=\det(A)=\prod_i \lambda_i$.

Q: How does trace = sum of eigenvalues give a quick sanity check when computing eigenvalues?
A: After finding candidate eigenvalues, add them up and compare to the sum of the diagonal entries of $A$. If the two disagree, there is an arithmetic error somewhere. Similarly, their product should equal $\det A$.

## 8.11 Algebraic vs Geometric Multiplicity

C: The [algebraic multiplicity] of an eigenvalue $\lambda$ is its multiplicity as a root of the characteristic polynomial $p(\lambda)=\det(A-\lambda I)$.

C: The [geometric multiplicity] of $\lambda$ is $\dim E_\lambda = \dim \text{Nul}(A - \lambda I)$, the dimension of its eigenspace.

C: For every eigenvalue, the geometric multiplicity is at most the [algebraic multiplicity].

Q: Why must geometric multiplicity be at least 1 for every eigenvalue?
A: Because $\lambda$ being an eigenvalue means $A-\lambda I$ is singular, so $\text{Nul}(A-\lambda I)$ is nontrivial. Its dimension is therefore at least 1, which is exactly the geometric multiplicity.

Q: What does it mean when geometric multiplicity is strictly less than algebraic multiplicity?
A: The eigenvalue is "defective": it appears as a repeated root of the characteristic polynomial but does not supply enough linearly independent eigenvectors. This is precisely what prevents a matrix from being diagonalizable.

## 8.12 Independence of Eigenvectors from Distinct Eigenvalues

C: Eigenvectors corresponding to [distinct eigenvalues] are linearly independent.

Q: Why are eigenvectors from distinct eigenvalues linearly independent?
A: Suppose a dependence $c_1\vec{v}_1+\cdots+c_k\vec{v}_k=\vec{0}$ with distinct $\lambda_i$. Applying $A$ and subtracting $\lambda_k$ times the original relation eliminates $\vec{v}_k$, leaving a shorter dependence with coefficients $c_i(\lambda_i-\lambda_k)$. Induction on $k$ forces all $c_i=0$, so the vectors are independent.

Q: What is a practical consequence of the distinct-eigenvalues theorem for diagonalization?
A: If an $n\times n$ matrix has $n$ distinct eigenvalues, picking one eigenvector per eigenvalue automatically gives $n$ linearly independent eigenvectors. Such a matrix is guaranteed to be diagonalizable.

## 8.13 Diagonalization

Q: Before learning the formula, predict: if $A$ has $n$ linearly independent eigenvectors, what should the matrix look like in the basis formed by those eigenvectors?
A: It should be diagonal, because $A$ simply scales each basis vector by its eigenvalue — there is no mixing between basis directions.

C: A square matrix $A$ is [diagonalizable] if it can be written $A = PDP^{-1}$ with $D$ diagonal and $P$ invertible.

C: In the factorization $A = PDP^{-1}$, the columns of $P$ are [eigenvectors] of $A$, and the diagonal entries of $D$ are the corresponding eigenvalues (in matching order).

Q: Why does $A = PDP^{-1}$ follow from having $n$ linearly independent eigenvectors?
A: Let $P$ have those eigenvectors as columns and let $D$ be diagonal with the matching eigenvalues. Then $AP = PD$ column by column, since $A\vec{v}_i = \lambda_i\vec{v}_i$. Because the columns of $P$ are independent, $P$ is invertible, giving $A = PDP^{-1}$.

Q: What is the role of $P$ in the factorization $A = PDP^{-1}$?
A: $P$ is the change-of-basis matrix from the eigenvector basis to the standard basis. Multiplying by $P^{-1}$ expresses a vector in the eigenvector coordinates, $D$ scales each coordinate, and $P$ converts back.

## 8.14 When Is $A$ Diagonalizable?

C: An $n\times n$ matrix $A$ is diagonalizable iff $A$ has [$n$ linearly independent eigenvectors].

C: Equivalently, $A$ is diagonalizable iff for every eigenvalue the [geometric multiplicity equals the algebraic multiplicity] (so the geometric multiplicities sum to $n$).

Q: Why is "$n$ linearly independent eigenvectors" the right condition for diagonalizability?
A: Those eigenvectors form a basis of $\mathbb{R}^n$ in which $A$ acts diagonally. Fewer than $n$ independent eigenvectors means the eigenvectors cannot span the space, so some directions are not scaled cleanly and no diagonal form exists.

Q: If all eigenvalues of an $n\times n$ matrix are distinct, why is it automatically diagonalizable?
A: Distinct eigenvalues give $n$ eigenvectors that are automatically linearly independent, so they form a basis of $\mathbb{R}^n$. Therefore $A$ has the $n$ independent eigenvectors required for $A=PDP^{-1}$.

## 8.15 A Non-Diagonalizable Example

Q: Give a simple $2\times 2$ real matrix that is not diagonalizable and explain why.
A: The shear $A=\begin{pmatrix}1 & 1\\ 0 & 1\end{pmatrix}$. Its characteristic polynomial is $(1-\lambda)^2$, so $\lambda=1$ has algebraic multiplicity 2, but $A-I=\begin{pmatrix}0&1\\0&0\end{pmatrix}$ has null space spanned only by $\begin{pmatrix}1\\0\end{pmatrix}$. Geometric multiplicity is 1, short of 2, so there are not enough independent eigenvectors.

C: The shear matrix $\begin{pmatrix}1 & 1\\ 0 & 1\end{pmatrix}$ has a single eigenvalue $\lambda=1$ with algebraic multiplicity $2$ but geometric multiplicity $[1]$, so it is not diagonalizable.

Q: Geometrically, why does a shear fail to be diagonalizable?
A: A shear fixes one line (the $x$-axis) but tilts every other line, so only one independent direction is stretched purely. There is no second direction left unchanged (up to scaling), so no basis of eigenvectors exists.

## 8.16 Computing $A^k$ via Diagonalization

C: If $A = PDP^{-1}$ with $D$ diagonal, then $A^k = [PD^kP^{-1}]$ for every positive integer $k$.

Q: Why does $A^k = PD^kP^{-1}$?
A: $A^k = (PDP^{-1})(PDP^{-1})\cdots(PDP^{-1})$. Adjacent $P^{-1}P$ collapse to $I$, leaving $PD^kP^{-1}$. Since $D$ is diagonal, $D^k$ is obtained simply by raising each diagonal entry to the $k$th power.

Q: Why does diagonalization make powers of $A$ dramatically cheaper to compute?
A: Directly computing $A^k$ requires $k$ matrix multiplications, each $O(n^3)$. With diagonalization, we do two matrix multiplications plus $n$ scalar powers — independent of $k$. This is crucial for dynamical systems, Markov chains, and matrix exponentials.

## 8.17 Complex Eigenvalues

Q: Why can a real matrix have complex eigenvalues?
A: The characteristic polynomial has real coefficients, but its roots can be complex. Geometrically, a real map with no invariant real line (like a rotation) cannot have real eigenvalues, yet it still has roots of its characteristic polynomial — those roots are complex.

C: Complex eigenvalues of a real matrix always occur in [complex conjugate pairs] $\lambda$ and $\bar\lambda$.

Q: Why do complex eigenvalues of a real matrix come in conjugate pairs?
A: The characteristic polynomial has real coefficients. If $\lambda$ is a root, taking the conjugate of $p(\lambda)=0$ gives $p(\bar\lambda)=0$, so $\bar\lambda$ is also a root. Hence non-real roots pair up.

Q: What are the eigenvalues of the $2\times 2$ rotation matrix $R_\theta=\begin{pmatrix}\cos\theta & -\sin\theta\\ \sin\theta & \cos\theta\end{pmatrix}$ and why are they typically complex?
A: The characteristic polynomial is $\lambda^2 - 2\cos\theta\,\lambda + 1$, with roots $\lambda = \cos\theta \pm i\sin\theta = e^{\pm i\theta}$. For $\theta\notin\{0,\pi\}$, the roots are non-real because a rotation leaves no real line fixed.

## 8.18 Procedural: Diagonalizing a $3\times 3$ Matrix

P: Diagonalize the matrix $A=\begin{pmatrix}2 & 0 & 0\\ 1 & 2 & 1\\ 1 & 0 & 3\end{pmatrix}$: find its eigenvalues, a basis of eigenvectors, matrices $P$ and $D$, and verify $A=PDP^{-1}$.

S:
**IDENTIFY**: A $3\times 3$ diagonalization task. We need the eigenvalues (roots of $\det(A-\lambda I)=0$), a basis of eigenvectors (null spaces of $A-\lambda I$), and a check that stacking them as columns of $P$ gives $A=PDP^{-1}$.

**PLAN**:
- Compute the characteristic polynomial $p(\lambda)=\det(A-\lambda I)$ and factor it.
- For each eigenvalue $\lambda_i$, row reduce $A-\lambda_i I$ and read off a basis of $E_{\lambda_i}=\text{Nul}(A-\lambda_i I)$.
- Assemble $P=[\vec{v}_1\ \vec{v}_2\ \vec{v}_3]$ and $D=\text{diag}(\lambda_1,\lambda_2,\lambda_3)$ in matching column order.
- Verify by checking $AP=PD$ column by column (equivalent to $A=PDP^{-1}$) and by the sanity checks $\text{trace}(A)=\sum\lambda_i$, $\det(A)=\prod\lambda_i$.

**EXECUTE**:
1. Characteristic polynomial. Since $A$ is lower triangular, $p(\lambda)=\det(A-\lambda I)=(2-\lambda)(2-\lambda)(3-\lambda)$. Eigenvalues: $\lambda_1=\lambda_2=2$ (algebraic multiplicity $2$) and $\lambda_3=3$ (algebraic multiplicity $1$).
2. Eigenspace for $\lambda=2$. $A-2I=\begin{pmatrix}0&0&0\\ 1&0&1\\ 1&0&1\end{pmatrix}$. Row reduction gives the single equation $v_1+v_3=0$, with $v_2$ free and $v_3$ free. A basis: $\vec{v}_1=\begin{pmatrix}0\\1\\0\end{pmatrix}$, $\vec{v}_2=\begin{pmatrix}-1\\0\\1\end{pmatrix}$. Geometric multiplicity is $2$, equal to algebraic multiplicity.
3. Eigenspace for $\lambda=3$. $A-3I=\begin{pmatrix}-1&0&0\\ 1&-1&1\\ 1&0&0\end{pmatrix}$. Row reduction yields $v_1=0$ and $-v_2+v_3=0$, so $v_2=v_3$ with $v_3$ free. A basis: $\vec{v}_3=\begin{pmatrix}0\\1\\1\end{pmatrix}$.
4. Assemble $P$ and $D$. Put the three eigenvectors as columns and the eigenvalues on the diagonal in the same order: $P=\begin{pmatrix}0 & -1 & 0\\ 1 & 0 & 1\\ 0 & 1 & 1\end{pmatrix}$, $D=\begin{pmatrix}2 & 0 & 0\\ 0 & 2 & 0\\ 0 & 0 & 3\end{pmatrix}$.
5. Verify $AP=PD$. Column 1: $A\vec{v}_1=\begin{pmatrix}0\\2\\0\end{pmatrix}=2\vec{v}_1$. Column 2: $A\vec{v}_2=\begin{pmatrix}-2\\0\\2\end{pmatrix}=2\vec{v}_2$. Column 3: $A\vec{v}_3=\begin{pmatrix}0\\3\\3\end{pmatrix}=3\vec{v}_3$. Each matches the corresponding column of $PD$, so $AP=PD$, hence $A=PDP^{-1}$ (since $P$ has independent columns and is invertible).

**EVALUATE**:
- Sanity check with trace and determinant: $\text{trace}(A)=2+2+3=7=\sum\lambda_i$; $\det(A)=2\cdot 2\cdot 3=12=\prod\lambda_i$. Both agree, confirming the eigenvalues.
- We found $3$ linearly independent eigenvectors (two for $\lambda=2$, one for $\lambda=3$), so geometric multiplicities sum to $3=n$, consistent with $A$ being diagonalizable.
- The repeated eigenvalue $\lambda=2$ did not block diagonalization here because its geometric multiplicity matched its algebraic multiplicity — unlike the shear in Section 8.15.
