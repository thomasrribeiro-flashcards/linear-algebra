+++
name = "Linear Algebra"
subject = "Math"
order = 1
tags = ["math", "linear-algebra", "linear-systems", "gaussian-elimination", "rref", "matrices"]
+++

# Linear Algebra — Systems of Linear Equations

## 1.1 Linear Equations

Q: Why do we study linear equations first in linear algebra?
A: Linear equations describe the simplest possible relationships between variables — each variable appears only to the first power and never multiplied by another variable. This simplicity lets us build powerful solution methods (like row reduction) that extend to matrices, vector spaces, and transformations. Nearly every advanced topic in linear algebra ultimately reduces to solving linear systems.

C: A [linear equation] in the variables $x_1, x_2, \ldots, x_n$ is an equation that can be written as $a_1 x_1 + a_2 x_2 + \cdots + a_n x_n = b$, where the $a_i$ and $b$ are constants.

C: In the linear equation $a_1 x_1 + \cdots + a_n x_n = b$, the numbers $a_1, \ldots, a_n$ are called the [coefficients] and $b$ is called the constant term.

Q: What makes $2x + 3y = 5$ a linear equation?
A: Each variable ($x$ and $y$) appears only to the first power, multiplied by a constant, and the terms are added together. No variable is squared, multiplied by another variable, or inside a nonlinear function.

Q: Why is $x^2 = 1$ not a linear equation?
A: The variable $x$ appears to the second power. Linear equations require every variable to appear only to the first power with a constant coefficient, so any exponent other than 1 disqualifies it.

C: The equation $xy = 4$ is [not linear] because it contains a product of two variables.

C: The equation $\sin(x) + y = 1$ is [not linear] because $x$ appears inside a nonlinear function.

## 1.2 Systems of Linear Equations

Q: Why do we care about systems of linear equations rather than single equations?
A: Real problems almost always involve several unknowns constrained by several conditions simultaneously. A single equation rarely pins down a unique answer, but a well-chosen system can. Understanding which systems have solutions — and how many — is the central question the rest of the subject answers.

C: A [system of linear equations] (or linear system) is a collection of one or more linear equations involving the same set of variables.

C: A [solution] of a linear system in variables $x_1, \ldots, x_n$ is a list of numbers $(s_1, \ldots, s_n)$ that makes every equation true when substituted for the variables.

C: The [solution set] of a linear system is the set of all possible solutions of the system.

C: A linear system is called [consistent] if it has at least one solution.

C: A linear system is called [inconsistent] if it has no solutions.

Q: What are the three possible outcomes for the number of solutions of a linear system?
A: A linear system has either no solution (inconsistent), exactly one solution (unique), or infinitely many solutions. No linear system can have, for example, exactly two or exactly five solutions — this trichotomy follows from the linear structure.

Q: Why can a linear system never have exactly two solutions?
A: If two distinct lists of values both satisfy every equation, then every weighted average of them also satisfies the equations (by linearity). So as soon as two solutions exist, infinitely many do.

## 1.3 Geometric Interpretation

Q: Why is a geometric picture of linear systems worth learning before the algebra?
A: Geometry turns abstract algebraic statements ("the system is inconsistent") into concrete images ("the lines are parallel"). This lets you predict the number of solutions before computing and builds intuition that survives into higher dimensions where pictures are harder.

C: In two variables, the graph of a single linear equation $a x + b y = c$ is a [line] in the plane (assuming $a$ and $b$ are not both zero).

C: In three variables, the graph of a single linear equation $a x + b y + c z = d$ is a [plane] in three-dimensional space (assuming $a, b, c$ are not all zero).

Q: Geometrically, what does a solution of a 2-variable linear system represent?
A: A point that lies on every line in the system simultaneously — that is, a point in the intersection of all the lines.

Q: Geometrically, when does a system of two equations in two variables have no solution?
A: When the two lines are parallel but distinct, so they never intersect.

Q: Geometrically, when does a system of two equations in two variables have infinitely many solutions?
A: When the two equations describe the same line, so every point on that line satisfies both.

Q: Geometrically, what does a solution of a 3-variable linear system represent?
A: A point that lies on every plane in the system — a point in the intersection of the planes.

## 1.4 Matrix Notation

Q: Why do we switch from equations to matrices?
A: Writing out variables and plus signs repeatedly is bulky and hides the structure. A matrix strips away the names and keeps only the numbers that matter, so row operations can be applied mechanically. This is the key efficiency that makes large systems tractable.

C: A [matrix] is a rectangular array of numbers.

C: A matrix with $m$ rows and $n$ columns is called an [$m \times n$ matrix], and $m \times n$ is called its size.

C: The [entry] in row $i$ and column $j$ of a matrix $A$ is denoted $a_{ij}$, where $i$ is the row index and $j$ is the column index.

Q: In the notation $a_{ij}$, which subscript comes first — row or column?
A: The row index comes first, then the column. So $a_{23}$ is the entry in row 2, column 3. This "rows before columns" convention is universal in linear algebra.

## 1.5 Coefficient Matrix and Augmented Matrix

C: The [coefficient matrix] of a linear system is the matrix whose entries are the coefficients $a_{ij}$ of the variables, one row per equation.

C: The [augmented matrix] of a linear system is the coefficient matrix with an extra column appended containing the constants $b_i$ from the right-hand sides.

Q: Why do we usually work with the augmented matrix rather than the coefficient matrix alone?
A: Row operations must be applied to both sides of every equation to preserve solutions. Keeping the constants in an extra column means a single row operation updates the coefficients and the constants together, making the bookkeeping automatic.

Q: For the system $2x + y = 3$, $x - y = 0$, what is the augmented matrix?
A: $\begin{pmatrix} 2 & 1 & 3 \\ 1 & -1 & 0 \end{pmatrix}$, where the first two columns hold the coefficients of $x$ and $y$ and the last column (often drawn with a vertical bar) holds the constants.

## 1.6 Elementary Row Operations

Q: Why are we allowed to modify a linear system without changing its solution set?
A: Two systems are equivalent (have the same solutions) if one can be obtained from the other by reversible manipulations that preserve truth. Swapping equations, scaling an equation by a nonzero constant, and adding a multiple of one equation to another are all reversible and truth-preserving — so they change the equations' appearance but not their solutions.

C: The three [elementary row operations] on a matrix are: (1) swap two rows, (2) scale a row by a nonzero constant, and (3) replace a row by itself plus a multiple of another row.

C: The row operation "[swap]" interchanges two rows of the matrix.

C: The row operation "[scale]" multiplies every entry of a single row by a nonzero constant $k$.

C: The row operation "[replacement]" replaces row $i$ by (row $i$) $+ k \cdot$ (row $j$), where $k$ is any scalar and $j \neq i$.

Q: Why must the scaling row operation use a nonzero constant?
A: Scaling by zero would wipe out the equation entirely, losing information and potentially introducing solutions that did not exist before. Restricting to nonzero constants keeps the operation reversible (dividing by the same constant undoes it) and preserves the solution set.

C: Two matrices are called [row equivalent] if one can be obtained from the other by a finite sequence of elementary row operations.

Q: Why does row equivalence guarantee equal solution sets?
A: Each elementary row operation is reversible and corresponds to a reversible manipulation of the underlying equations. So any solution of the original system also satisfies the new system, and vice versa.

## 1.7 Row Echelon Form

Q: Why reduce a matrix to a "staircase" shape at all?
A: A staircase (echelon) pattern lets you read off information easily: variables with leading entries are determined by the later ones, and rows of zeros flag either redundancy or inconsistency. It is the simplest intermediate form from which solutions can be extracted.

C: In a matrix row, the [leading entry] is the leftmost nonzero entry of that row.

C: A matrix is in [row echelon form] (REF) if: (1) all zero rows are at the bottom, and (2) each leading entry is strictly to the right of the leading entry in the row above it.

C: In a row echelon matrix, a [pivot position] is the location of a leading entry in a nonzero row.

C: In a row echelon matrix, a [pivot column] is a column that contains a pivot position.

Q: Why must every zero row sit at the bottom in row echelon form?
A: A zero row carries no constraint. Pushing zero rows to the bottom exposes the staircase pattern of the nonzero rows and makes it obvious how many real equations remain.

## 1.8 Reduced Row Echelon Form

C: A matrix is in [reduced row echelon form] (RREF) if it is in row echelon form AND every leading entry is 1 AND each leading 1 is the only nonzero entry in its column.

C: In RREF, every leading entry equals [1] and is the only nonzero entry in its column.

Q: Why bother going all the way to RREF rather than stopping at REF?
A: RREF is unique — each matrix has exactly one reduced row echelon form. This means the final answer doesn't depend on the order of operations chosen, and solutions can be read off directly without any back-substitution.

Q: Why is the reduced row echelon form of a matrix unique, while the row echelon form is not?
A: Different sequences of row operations can produce different REFs (leading entries need not be 1 and columns above leading entries need not be zeroed). RREF eliminates those choices by demanding leading 1s and zeros above them, which determines every entry exactly.

## 1.9 Gaussian Elimination (Forward Phase)

Q: Why split elimination into a "forward" and a "backward" phase?
A: The forward phase only needs to produce zeros below each pivot, reaching row echelon form. Checking consistency and counting pivots can be done at that point, avoiding unnecessary work. The backward phase then cleans up above the pivots only if a full solution is needed.

C: [Gaussian elimination] is the forward phase of row reduction: use row operations to bring a matrix to row echelon form by creating zeros below each pivot, working left to right, top to bottom.

Q: What is the algorithm for Gaussian elimination (forward phase)?
A: Find the leftmost nonzero column; if necessary swap a nonzero entry into the top position to serve as a pivot; use replacement operations to zero out all entries below that pivot; then cover that row and repeat on the remaining submatrix.

## 1.10 Gauss-Jordan Elimination (Backward Phase)

C: [Gauss-Jordan elimination] adds a backward phase to Gaussian elimination: starting from REF, scale each pivot to 1 and use replacement operations to create zeros above every pivot, producing RREF.

Q: Why does Gauss-Jordan elimination produce RREF rather than just REF?
A: The backward phase explicitly forces each leading entry to be 1 (via scaling) and zeros out the entries directly above every pivot (via replacement). Those are exactly the two extra conditions RREF requires beyond REF.

## 1.11 Reading Solutions from RREF

C: In the RREF of an augmented matrix, the variables corresponding to pivot columns are called [basic variables] (or pivot variables).

C: In the RREF of an augmented matrix, the variables corresponding to non-pivot columns (among the variable columns) are called [free variables].

Q: Why are non-pivot variables called "free"?
A: In RREF, each basic variable is expressed in terms of the free variables alone. This means the free variables can take any real value, and each choice generates a different solution — they are literally free to be chosen.

C: The [parametric form] of a solution expresses each basic variable as a function of the free variables, with the free variables serving as parameters.

Q: How do you obtain parametric form from the RREF of an augmented matrix?
A: Translate each nonzero row back into an equation, then solve each equation for its basic variable in terms of the free variables on the right side. Assign parameter names to the free variables, and write each basic variable as the resulting expression.

Q: In an augmented matrix's RREF, what does a row of the form $(0 \; 0 \; \cdots \; 0 \; | \; b)$ with $b \neq 0$ indicate?
A: Inconsistency — the row encodes the equation $0 = b$, which is false. The original system has no solutions.

## 1.12 Existence and Uniqueness Theorem

Q: Why do we need a theorem that simply counts pivot columns?
A: Once a system is in RREF, existence (is there a solution?) and uniqueness (is it the only one?) each depend on a simple structural feature — whether the augmented column is a pivot column, and whether every variable column is a pivot column. Phrasing this as a theorem turns row reduction into a complete decision procedure.

C: [Existence and Uniqueness Theorem] (part 1): A linear system is consistent if and only if the rightmost column of its augmented matrix is NOT a pivot column.

C: [Existence and Uniqueness Theorem] (part 2): A consistent system has a unique solution if and only if there are no free variables (every variable column is a pivot column).

Q: If a consistent linear system has at least one free variable, how many solutions does it have?
A: Infinitely many. Each free variable can take any real value independently, and each choice produces a distinct solution.

## 1.13 Homogeneous Systems

C: A linear system is called [homogeneous] if it can be written as $A \vec{x} = \vec{0}$, i.e., every constant term on the right-hand side is zero.

C: Every homogeneous system has at least the solution $\vec{x} = \vec{0}$, called the [trivial solution].

Q: Why is every homogeneous system automatically consistent?
A: Substituting $\vec{x} = \vec{0}$ (all variables equal to zero) makes every left-hand side zero, which already matches the zero right-hand side. So the trivial solution always exists, and inconsistency is impossible.

C: A solution $\vec{x} \neq \vec{0}$ of a homogeneous system is called a [nontrivial solution].

Q: When does a homogeneous system $A \vec{x} = \vec{0}$ have a nontrivial solution?
A: If and only if the system has at least one free variable. By the existence-and-uniqueness theorem, a consistent system with a free variable has infinitely many solutions, so it has solutions other than $\vec{0}$. If every variable is basic, the only solution is trivial.

Q: Why does having more variables than equations in a homogeneous system guarantee a nontrivial solution?
A: The number of pivots cannot exceed the number of equations (rows). If there are more variables (columns) than equations, some variable column must be a non-pivot column — so a free variable exists, guaranteeing infinitely many solutions including nontrivial ones.

## 1.14 Worked Problem: Solving a 3×3 System

P: Solve the following system using Gauss-Jordan elimination, and identify any free variables: $x + 2y + z = 4$, $2x + 5y + 3z = 11$, $x + 3y + 2z = 7$.

S:
**IDENTIFY**: A $3 \times 3$ linear system. Goal: reduce the augmented matrix to RREF, then read the solution and classify each variable as basic or free.

**PLAN**:
- Write the augmented matrix.
- Forward phase: create zeros below pivots to reach REF.
- Backward phase: scale pivots to 1 and create zeros above pivots to reach RREF.
- Read solutions; any non-pivot variable column corresponds to a free variable.

**EXECUTE**:
1. Augmented matrix:
$$\left(\begin{array}{ccc|c} 1 & 2 & 1 & 4 \\ 2 & 5 & 3 & 11 \\ 1 & 3 & 2 & 7 \end{array}\right)$$
2. $R_2 \to R_2 - 2R_1$ and $R_3 \to R_3 - R_1$:
$$\left(\begin{array}{ccc|c} 1 & 2 & 1 & 4 \\ 0 & 1 & 1 & 3 \\ 0 & 1 & 1 & 3 \end{array}\right)$$
3. $R_3 \to R_3 - R_2$:
$$\left(\begin{array}{ccc|c} 1 & 2 & 1 & 4 \\ 0 & 1 & 1 & 3 \\ 0 & 0 & 0 & 0 \end{array}\right)$$
   REF reached. Pivot columns: 1 and 2. Column 3 is a non-pivot variable column, so $z$ is a free variable.
4. Backward phase — $R_1 \to R_1 - 2 R_2$:
$$\left(\begin{array}{ccc|c} 1 & 0 & -1 & -2 \\ 0 & 1 & 1 & 3 \\ 0 & 0 & 0 & 0 \end{array}\right)$$
   This is RREF.
5. Read equations: $x - z = -2$ and $y + z = 3$. Let $z = t$ be the free parameter. Then $x = -2 + t$ and $y = 3 - t$.

**EVALUATE**:
- Free variable: $z$ (one free variable, so infinitely many solutions).
- Parametric form: $(x, y, z) = (-2 + t,\; 3 - t,\; t)$ for $t \in \mathbb{R}$.
- Check with $t = 0$: $(-2, 3, 0)$ gives $-2 + 6 + 0 = 4$ ✓, $-4 + 15 + 0 = 11$ ✓, $-2 + 9 + 0 = 7$ ✓.
- Consistent with the existence-and-uniqueness theorem: the rightmost column is not a pivot column (consistent), and there is a free variable (infinitely many solutions).
