+++
order = 11
tags = ["math", "linear-algebra", "least-squares", "normal-equations", "regression", "projection"]
+++

# Linear Algebra — Least Squares

## 11.1 The Setup: When $A\vec{x} = \vec{b}$ Has No Solution

Q: Why might the linear system $A\vec{x} = \vec{b}$ have no exact solution?
A: The system is solvable iff $\vec{b} \in \text{Col}(A)$, i.e., $\vec{b}$ is a linear combination of the columns of $A$. When $\vec{b} \notin \text{Col}(A)$, no choice of $\vec{x}$ produces $A\vec{x} = \vec{b}$ exactly. This is common in overdetermined systems (more equations than unknowns) arising from noisy measurements, where the data points do not lie exactly on any linear model.

C: The equation $A\vec{x} = \vec{b}$ has an exact solution if and only if $\vec{b}$ lies in [$\text{Col}(A)$], the column space of $A$.

Q: In practice, when do we encounter systems $A\vec{x} = \vec{b}$ that have no solution?
A: Whenever we fit a model to more data points than parameters. For example, fitting a line ($2$ parameters) through $100$ noisy measurements produces $100$ equations in $2$ unknowns, which almost never has an exact solution.

Q: Before we define it, predict: if $A\vec{x} = \vec{b}$ has no solution, what would be a sensible "best guess" for $\vec{x}$?
A: Choose $\vec{x}$ to make $A\vec{x}$ as close as possible to $\vec{b}$, i.e., minimize the error $\vec{b} - A\vec{x}$ in some norm. This is exactly the idea behind least squares.

## 11.2 The Least-Squares Problem

C: A [least-squares solution] $\hat{\vec{x}}$ of $A\vec{x} = \vec{b}$ is any vector that minimizes $\|\vec{b} - A\vec{x}\|$, where $\|\cdot\|$ is the Euclidean norm.

Q: What quantity does a least-squares solution minimize?
A: The Euclidean norm of the residual, $\|\vec{b} - A\vec{x}\|$, where $\vec{b}$ is the target vector and $A\vec{x}$ is the model prediction. Equivalently, it minimizes the squared norm $\|\vec{b} - A\vec{x}\|^2$.

C: The vector $\vec{r} = \vec{b} - A\hat{\vec{x}}$ is called the [residual] vector, measuring the error between the target $\vec{b}$ and the best approximation $A\hat{\vec{x}}$.

## 11.3 Why Minimize the Norm-Squared?

Q: Why do we minimize $\|\vec{b} - A\vec{x}\|^2$ rather than $\|\vec{b} - A\vec{x}\|$?
A: The two have the same minimizer since squaring is monotonic on non-negative values. But the squared norm is a smooth quadratic in $\vec{x}$, so calculus (gradient = $\vec{0}$) gives clean linear equations. The un-squared norm has a square root that complicates differentiation.

Q: Why use the Euclidean (2-norm) rather than, say, the 1-norm or $\infty$-norm?
A: The 2-norm penalizes each coordinate error quadratically, producing a smooth strictly convex objective with a unique closed-form solution via linear algebra. It also matches the "sum of squared errors" minimized in Gaussian maximum-likelihood estimation, giving least squares a statistical justification.

C: Minimizing $\|\vec{b} - A\vec{x}\|^2 = \sum_i (b_i - (A\vec{x})_i)^2$ corresponds to minimizing the [sum of squared errors] in statistics.

## 11.4 Geometric Interpretation

Q: Geometrically, what is $A\hat{\vec{x}}$ when $\hat{\vec{x}}$ is a least-squares solution?
A: $A\hat{\vec{x}}$ is the orthogonal projection of $\vec{b}$ onto $\text{Col}(A)$. Among all vectors in $\text{Col}(A)$, the projection is the unique one closest to $\vec{b}$, by the best-approximation property of orthogonal projection.

C: If $\hat{\vec{x}}$ is a least-squares solution of $A\vec{x} = \vec{b}$, then $A\hat{\vec{x}} = [\text{proj}_{\text{Col}(A)}\vec{b}]$, the orthogonal projection of $\vec{b}$ onto the column space.

Q: Why does the best-approximation property of orthogonal projection guarantee $A\hat{\vec{x}}$ is the projection of $\vec{b}$ onto $\text{Col}(A)$?
A: As $\vec{x}$ ranges over $\mathbb{R}^n$, the vector $A\vec{x}$ ranges over all of $\text{Col}(A)$. Minimizing $\|\vec{b} - A\vec{x}\|$ is therefore minimizing the distance from $\vec{b}$ to $\text{Col}(A)$, and that minimum is achieved exactly at the orthogonal projection.

## 11.5 The Normal Equations

Q: Why must the residual $\vec{r} = \vec{b} - A\hat{\vec{x}}$ be orthogonal to $\text{Col}(A)$?
A: Because $A\hat{\vec{x}}$ is the orthogonal projection of $\vec{b}$ onto $\text{Col}(A)$, the remainder $\vec{b} - A\hat{\vec{x}}$ lies in the orthogonal complement $\text{Col}(A)^\perp$. This orthogonality is precisely what makes the projection the closest point.

Q: Why does $\vec{b} - A\hat{\vec{x}} \in \text{Col}(A)^\perp$ imply $A^T(\vec{b} - A\hat{\vec{x}}) = \vec{0}$?
A: From a previous chapter, $\text{Col}(A)^\perp = \text{Nul}(A^T)$. So the residual being in the orthogonal complement of the column space is equivalent to $A^T$ annihilating it: $A^T(\vec{b} - A\hat{\vec{x}}) = \vec{0}$.

C: The [normal equations] for least squares are $A^TA\hat{\vec{x}} = A^T\vec{b}$.

Q: How do you derive the normal equations from the orthogonality of the residual?
A: The residual $\vec{b} - A\hat{\vec{x}}$ lies in $\text{Col}(A)^\perp = \text{Nul}(A^T)$, so $A^T(\vec{b} - A\hat{\vec{x}}) = \vec{0}$. Expanding gives $A^T\vec{b} - A^TA\hat{\vec{x}} = \vec{0}$, i.e., $A^TA\hat{\vec{x}} = A^T\vec{b}$.

C: The identity $\text{Col}(A)^\perp = [\text{Nul}(A^T)]$ is the key fact that converts "residual is orthogonal to every column of $A$" into the normal equations.

## 11.6 Existence of Solutions

Q: Why does the least-squares problem always have at least one solution?
A: The projection $\text{proj}_{\text{Col}(A)}\vec{b}$ exists for any $\vec{b}$, and it lies in $\text{Col}(A)$ by definition. Therefore some $\hat{\vec{x}}$ must satisfy $A\hat{\vec{x}} = \text{proj}_{\text{Col}(A)}\vec{b}$. Equivalently, $A^T\vec{b}$ always lies in $\text{Col}(A^TA)$, so $A^TA\hat{\vec{x}} = A^T\vec{b}$ is always consistent.

C: The least-squares problem $\min_{\vec{x}} \|\vec{b} - A\vec{x}\|$ [always has at least one solution], regardless of $A$ or $\vec{b}$.

## 11.7 Uniqueness of Solutions

Q: When does the least-squares problem have a unique solution?
A: Exactly when the columns of $A$ are linearly independent. Equivalently, when $\text{Nul}(A) = \{\vec{0}\}$, or when $A^TA$ is invertible. If the columns are dependent, then any $\vec{v} \in \text{Nul}(A)$ added to $\hat{\vec{x}}$ gives another least-squares solution.

C: The least-squares solution is unique iff the columns of $A$ are [linearly independent].

C: The matrix $A^TA$ is invertible iff the columns of $A$ are [linearly independent].

Q: Why is $A^TA$ invertible iff the columns of $A$ are linearly independent?
A: $A^TA\vec{x} = \vec{0}$ implies $\vec{x}^TA^TA\vec{x} = \|A\vec{x}\|^2 = 0$, so $A\vec{x} = \vec{0}$. Hence $\text{Nul}(A^TA) = \text{Nul}(A)$. So $A^TA$ (a square matrix) is invertible iff $\text{Nul}(A) = \{\vec{0}\}$, iff the columns of $A$ are independent.

## 11.8 Closed-Form Solution

C: When the columns of $A$ are linearly independent, the unique least-squares solution is $\hat{\vec{x}} = [(A^TA)^{-1}A^T\vec{b}]$.

Q: Why is the closed-form $\hat{\vec{x}} = (A^TA)^{-1}A^T\vec{b}$ only valid when columns of $A$ are independent?
A: This formula requires inverting $A^TA$, and $A^TA$ is invertible iff the columns of $A$ are linearly independent. Otherwise, $A^TA$ is singular and we need a pseudoinverse or a minimum-norm solution instead.

Q: Even when the closed-form $\hat{\vec{x}} = (A^TA)^{-1}A^T\vec{b}$ is valid, why do we usually not compute $(A^TA)^{-1}$ explicitly?
A: Explicit matrix inversion is numerically unstable and expensive. In practice we solve the linear system $A^TA\hat{\vec{x}} = A^T\vec{b}$ by factorization (Cholesky, or better, QR on $A$ itself), which is faster and more accurate.

## 11.9 Least-Squares Error

C: The [least-squares error] of $\hat{\vec{x}}$ is the residual norm $\|\vec{b} - A\hat{\vec{x}}\|$.

Q: What does a small least-squares error $\|\vec{b} - A\hat{\vec{x}}\|$ tell you?
A: That $\vec{b}$ is close to $\text{Col}(A)$, meaning the model $A\vec{x}$ can explain the target $\vec{b}$ well. A zero error means $\vec{b} \in \text{Col}(A)$ exactly, and $\hat{\vec{x}}$ is an exact solution of $A\vec{x} = \vec{b}$.

Q: What does a large least-squares error indicate about the model?
A: Either the data is very noisy, or the model class (the columns of $A$) cannot capture the structure of $\vec{b}$. The latter is underfitting: a richer set of columns (more basis functions) may be needed.

## 11.10 Least Squares via QR Factorization

Q: If $A = QR$ with $Q$ having orthonormal columns and $R$ upper triangular, how do the normal equations simplify?
A: Substituting $A = QR$ into $A^TA\hat{\vec{x}} = A^T\vec{b}$ gives $R^TQ^TQR\hat{\vec{x}} = R^TQ^T\vec{b}$. Since $Q^TQ = I$ and $R^T$ is invertible (columns of $A$ independent), this reduces to $R\hat{\vec{x}} = Q^T\vec{b}$.

C: Using the QR factorization $A = QR$, the normal equations reduce to $[R\hat{\vec{x}} = Q^T\vec{b}]$, which is solved by back-substitution.

Q: Why is solving least squares via QR more numerically stable than forming $A^TA$ directly?
A: The condition number of $A^TA$ is the square of the condition number of $A$, so forming $A^TA$ amplifies roundoff errors. QR avoids this: it works with $A$ directly, and triangular back-substitution on $R$ inherits only the condition number of $A$.

C: The condition number of $A^TA$ is the [square] of the condition number of $A$, which is why forming the normal equations explicitly loses numerical precision.

## 11.11 Application: Linear Regression

Q: How do you set up least squares to fit the line $y = \beta_0 + \beta_1 x$ to data points $(x_1, y_1), \ldots, (x_m, y_m)$?
A: Stack the equations $\beta_0 + \beta_1 x_i = y_i$ into matrix form. The design matrix has rows $[1, x_i]$, the unknown vector is $\vec{\beta} = (\beta_0, \beta_1)^T$, and the target is $\vec{y} = (y_1, \ldots, y_m)^T$. Then solve $A^TA\hat{\vec{\beta}} = A^T\vec{y}$.

C: For linear regression $y = \beta_0 + \beta_1 x$ on $m$ data points, the [design matrix] $A$ has rows $[1, x_i]$, where $x_i$ is the $i$-th input and each $1$ corresponds to the intercept column.

Q: In simple linear regression, what is the geometric meaning of minimizing $\sum_i (y_i - \beta_0 - \beta_1 x_i)^2$?
A: Each term is the squared vertical distance from data point $(x_i, y_i)$ to the line. Summing gives the total squared vertical error. Least squares finds the line minimizing this total, geometrically the line closest to the data in the vertical sense.

## 11.12 Fitting Polynomials and General Basis Functions

Q: How do you fit a quadratic $y = \beta_0 + \beta_1 x + \beta_2 x^2$ to data using least squares?
A: Build a design matrix $A$ with rows $[1, x_i, x_i^2]$ and target $\vec{y} = (y_1, \ldots, y_m)^T$. Solve $A^TA\hat{\vec{\beta}} = A^T\vec{y}$ for $\hat{\vec{\beta}} = (\beta_0, \beta_1, \beta_2)^T$. The fit is still linear in the parameters $\beta_j$, even though the model is nonlinear in $x$.

C: Polynomial regression $y = \sum_{j=0}^d \beta_j x^j$ is a least-squares problem because the unknowns $\beta_j$ enter [linearly], even though $x$ appears to higher powers.

Q: How do you fit a general model $y = \sum_{j=1}^k \beta_j \phi_j(x)$ where $\phi_j$ are fixed basis functions?
A: Build the design matrix $A$ with entries $A_{ij} = \phi_j(x_i)$, where $x_i$ is the $i$-th input. Then solve $A^TA\hat{\vec{\beta}} = A^T\vec{y}$. Any model linear in the coefficients $\beta_j$ (polynomials, sinusoids, splines, radial basis functions) reduces to least squares.

C: Any model of the form $y = \sum_j \beta_j \phi_j(x)$ with fixed basis functions $\phi_j$ can be fit by least squares because it is [linear in the unknown coefficients] $\beta_j$.

## 11.13 The Pseudoinverse

C: When $A$ has linearly independent columns, the matrix $A^+ = [(A^TA)^{-1}A^T]$ is called the (Moore–Penrose) pseudoinverse of $A$.

Q: Why is $(A^TA)^{-1}A^T$ called the pseudoinverse of $A$ (in the full-column-rank case)?
A: It plays the role an inverse would if $A$ were square and invertible: it left-inverts $A$, since $(A^TA)^{-1}A^T A = I$, and $\hat{\vec{x}} = A^+\vec{b}$ is the unique best solution to $A\vec{x} = \vec{b}$. For square invertible $A$, $A^+$ reduces to $A^{-1}$.

C: For a matrix $A$ with linearly independent columns, the pseudoinverse satisfies $A^+A = [I]$, the identity on $\mathbb{R}^n$.

Q: What does $AA^+$ represent geometrically when $A$ has linearly independent columns?
A: $AA^+ = A(A^TA)^{-1}A^T$ is the projection matrix onto $\text{Col}(A)$. Applying it to $\vec{b}$ gives $A\hat{\vec{x}}$, the closest point in $\text{Col}(A)$ to $\vec{b}$.

C: When $A$ has independent columns, the projection matrix onto $\text{Col}(A)$ is $[A(A^TA)^{-1}A^T]$.

## 11.14 Worked Example: Fitting a Line

P: Fit a least-squares line $y = \beta_0 + \beta_1 x$ to the four data points $(0, 1)$, $(1, 3)$, $(2, 4)$, $(3, 6)$ using the normal equations.

S:
**IDENTIFY**: Simple linear regression via least squares. Unknowns are the intercept $\beta_0$ and slope $\beta_1$; four data points give an overdetermined system.

**PLAN**:
- Build the design matrix $A$ with rows $[1, x_i]$ (one per data point) and the target vector $\vec{y}$
- Compute $A^TA$ and $A^T\vec{y}$
- Solve the normal equations $A^TA\hat{\vec{\beta}} = A^T\vec{y}$ for $\hat{\vec{\beta}} = (\beta_0, \beta_1)^T$
- Report the fitted line and compute the residual norm to evaluate fit quality

**EXECUTE**:
1. Design matrix and target:
$$A = \begin{pmatrix} 1 & 0 \\ 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{pmatrix}, \qquad \vec{y} = \begin{pmatrix} 1 \\ 3 \\ 4 \\ 6 \end{pmatrix}$$
2. Compute $A^TA$:
$$A^TA = \begin{pmatrix} 4 & 6 \\ 6 & 14 \end{pmatrix}$$
3. Compute $A^T\vec{y}$:
$$A^T\vec{y} = \begin{pmatrix} 1+3+4+6 \\ 0+3+8+18 \end{pmatrix} = \begin{pmatrix} 14 \\ 29 \end{pmatrix}$$
4. Solve $A^TA\hat{\vec{\beta}} = A^T\vec{y}$. The determinant is $4\cdot 14 - 6\cdot 6 = 56 - 36 = 20$, so
$$(A^TA)^{-1} = \frac{1}{20}\begin{pmatrix} 14 & -6 \\ -6 & 4 \end{pmatrix}$$
5. Therefore
$$\hat{\vec{\beta}} = \frac{1}{20}\begin{pmatrix} 14 & -6 \\ -6 & 4 \end{pmatrix}\begin{pmatrix} 14 \\ 29 \end{pmatrix} = \frac{1}{20}\begin{pmatrix} 196 - 174 \\ -84 + 116 \end{pmatrix} = \frac{1}{20}\begin{pmatrix} 22 \\ 32 \end{pmatrix} = \begin{pmatrix} 1.1 \\ 1.6 \end{pmatrix}$$
6. Fitted line: $y = 1.1 + 1.6x$.

**EVALUATE**:
- Check predictions vs data: at $x = 0, 1, 2, 3$ the line predicts $1.1, 2.7, 4.3, 5.9$; data is $1, 3, 4, 6$. Residuals: $-0.1, 0.3, -0.3, 0.1$, all small.
- Residual norm: $\|\vec{r}\| = \sqrt{0.01 + 0.09 + 0.09 + 0.01} = \sqrt{0.20} \approx 0.447$.
- Residuals sum to zero ($-0.1 + 0.3 - 0.3 + 0.1 = 0$), as expected when the design matrix includes an intercept column: the residual is orthogonal to the all-ones column.
- Slope $1.6$ and intercept $1.1$ are reasonable given the data trends upward roughly $1.6$ per unit $x$ from $y \approx 1$.
