+++
order = 4
subject = "mathematics"
tags = ["math", "linear-algebra", "vector-spaces", "subspaces", "null-space", "column-space", "span"]
+++

# Linear Algebra — Vector Spaces and Subspaces

## 4.1 Why Abstract Vector Spaces

Q: Why do we define "vector space" abstractly instead of just using $\mathbb{R}^n$?
A: Many mathematical objects — polynomials, matrices, continuous functions, solutions of linear differential equations — satisfy the same algebraic rules as arrows in $\mathbb{R}^n$. Abstracting these rules lets us prove one theorem about "linear combinations" and apply it everywhere, rather than re-proving it for each setting.

Q: What do arrows in $\mathbb{R}^3$, polynomials of degree $\le 5$, and $3\times 3$ matrices have in common algebraically?
A: You can add any two of them and get another of the same kind, and you can scale any of them by a real number and get another of the same kind. These two operations obey the same distributive, associative, and commutative laws in every case.

C: The point of an abstract vector space is to unify $\mathbb{R}^n$, [polynomials], matrices, and functions under a single set of axioms.

Q: What is gained by proving a result for abstract vector spaces rather than just $\mathbb{R}^n$?
A: Any theorem proved from the axioms automatically applies to every example — polynomials, matrices, function spaces — with no extra work. This is the power of abstraction: one proof, many applications.

## 4.2 Vector Space Axioms

Q: Before the formal axioms: predict what properties a "vector-space-like" set $V$ must satisfy if it should behave like $\mathbb{R}^n$.
A: You should be able to add any two elements (closure), scale by any real (closure), and have a zero and inverses; addition should be commutative and associative; scaling should distribute over addition. The ten axioms formalize exactly this.

Q: What is a vector space, informally?
A: A set $V$ together with an "addition" operation and a "scalar multiplication" operation that behave like addition and scaling of arrows in $\mathbb{R}^n$ — satisfying ten specific axioms about closure, associativity, commutativity, identities, inverses, and distributivity.

Q: To distinguish the closure axioms from the identity/inverse axioms: which one fails for "polynomials of degree exactly $n$"?
A: Closure under addition fails ($x^n + (-x^n) = 0$ has degree 0, not $n$). The identity/inverse axioms also fail (no zero polynomial in the set), but closure is the cleanest counter-example.

C: A vector space requires closure under two operations: [vector addition] and [scalar multiplication].

C: For a vector space, if $\vec{u},\vec{v}\in V$, then $\vec{u}+\vec{v}$ must also lie [in $V$] (closure under addition).

C: For a vector space, if $\vec{v}\in V$ and $c$ is a scalar, then $c\vec{v}$ must also lie [in $V$] (closure under scalar multiplication).

C: The additive identity axiom says $V$ must contain a [zero vector $\vec{0}$] such that $\vec{v}+\vec{0}=\vec{v}$ for every $\vec{v}\in V$.

C: The additive inverse axiom says for every $\vec{v}\in V$ there exists $-\vec{v}\in V$ with [$\vec{v}+(-\vec{v})=\vec{0}$].

C: Vector addition must be [commutative]: $\vec{u}+\vec{v}=\vec{v}+\vec{u}$.

C: Scalar multiplication distributes over vector addition: $c(\vec{u}+\vec{v})=$ [$c\vec{u}+c\vec{v}$], where $c$ is a scalar and $\vec{u},\vec{v}\in V$.

C: Scalar multiplication distributes over scalar addition: $(c+d)\vec{v}=$ [$c\vec{v}+d\vec{v}$], where $c,d$ are scalars and $\vec{v}\in V$.

C: The scalar identity axiom says [$1\vec{v}=\vec{v}$] for every $\vec{v}\in V$.

Q: Why must the zero vector be unique in a vector space?
A: Suppose $\vec{0}_1$ and $\vec{0}_2$ are both zero vectors. Then $\vec{0}_1 = \vec{0}_1 + \vec{0}_2 = \vec{0}_2$ using the identity axiom twice. Uniqueness follows directly from the axioms, so we talk about "the" zero vector.

## 4.3 Examples of Vector Spaces

C: The space $\mathbb{R}^n$ consists of all [$n$-tuples of real numbers] with componentwise addition and scalar multiplication.

C: The vector space $\mathbb{P}_n$ is the set of all polynomials of degree [at most $n$] with real coefficients.

Q: Why is $\mathbb{P}_n$ (polynomials of degree $\le n$) a vector space?
A: Adding two polynomials of degree $\le n$ gives a polynomial of degree $\le n$, and scaling one by a real number does the same — so it is closed under both operations. The zero polynomial acts as $\vec{0}$, and every axiom follows from ordinary polynomial arithmetic.

Q: Is the set of polynomials of degree exactly $n$ a vector space? Why or why not?
A: No. Adding $x^n$ and $-x^n + 1$ (both of "exact" degree $n$) gives $1$, which has degree $0$, so the set is not closed under addition. It also lacks a zero vector.

C: The space $M_{m\times n}$ consists of all [$m\times n$ matrices] with real entries, under matrix addition and scalar multiplication.

C: The space $C\lbrack a,b\rbrack $ consists of all [continuous real-valued functions] defined on the interval $\lbrack a,b\rbrack $, with pointwise addition and scalar multiplication.

Q: Why is $C[a,b]$ (continuous functions on $[a,b]$) a vector space?
A: The sum of two continuous functions is continuous, and a scalar multiple of a continuous function is continuous, so the set is closed under both operations. The zero function plays the role of $\vec{0}$, and the usual algebraic laws of real numbers force every remaining axiom to hold.

C: The trivial vector space is [$\{\vec{0}\}$] — the set containing only the zero vector.

Q: Why does the singleton $\{\vec{0}\}$ qualify as a vector space?
A: Every sum $\vec{0}+\vec{0}=\vec{0}$ and every scalar multiple $c\vec{0}=\vec{0}$ stays inside the set, so closure holds. All ten axioms are satisfied vacuously because the only element is the zero vector itself.

## 4.4 Subspaces

Q: What is a subspace of a vector space $V$?
A: A subset $H\subseteq V$ that is itself a vector space under the same addition and scalar multiplication. Instead of verifying all ten axioms, it suffices to check three closure conditions, because the other axioms are inherited from $V$.

C: A subset $H\subseteq V$ is a subspace if: (1) $\vec{0}\in H$, (2) $H$ is closed under [addition], and (3) $H$ is closed under [scalar multiplication].

Q: Why does the subspace test only require three conditions, not all ten axioms?
A: The associative, commutative, distributive, and identity axioms automatically hold for elements of $H$ because they already hold in the bigger space $V$. Only closure, containing $\vec{0}$, and having inverses need checking — and closure under scalar multiplication by $-1$ provides the inverses.

Q: Why is "contains $\vec{0}$" usually the first thing you check for a subspace?
A: It is fast to verify, it rules out most non-subspaces immediately (lines and planes not through the origin, affine sets, etc.), and without $\vec{0}$ the set cannot be a vector space at all.

Q: If $H$ is closed under scalar multiplication and $H$ is nonempty, why does $H$ automatically contain $\vec{0}$?
A: Pick any $\vec{v}\in H$. Then $0\cdot\vec{v}=\vec{0}$ must also lie in $H$ by closure under scalar multiplication. So for nonempty sets, "closed under scalar multiplication" already forces $\vec{0}\in H$.

## 4.5 Common Subspaces

C: In $\mathbb{R}^2$ and $\mathbb{R}^3$, every [line through the origin] is a subspace.

C: In $\mathbb{R}^3$, every [plane through the origin] is a subspace.

Q: Why is a line that does NOT pass through the origin not a subspace of $\mathbb{R}^2$?
A: It fails to contain $\vec{0}$, so subspace condition (1) is violated. Adding two points on such a line also lands off the line, so it fails closure under addition too.

Q: Why must every subspace contain the origin?
A: Taking the scalar $0$ times any vector in the subspace gives $\vec{0}$, and closure under scalar multiplication forces $\vec{0}$ to be in the subspace. Geometrically: scaling any vector down to zero length lands at the origin.

Q: What are the two "trivial" subspaces that every vector space $V$ has?
A: The zero subspace $\{\vec{0}\}$ and $V$ itself. Every other subspace lies strictly between these two.

## 4.6 Span

C: Given vectors $\vec{v}_1,\ldots,\vec{v}_k\in V$, their span $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\}$ is the set of all [linear combinations] $c_1\vec{v}_1+\cdots+c_k\vec{v}_k$, where $c_1,\ldots,c_k$ are real scalars.

Q: Why is $\text{span}\{\vec{v}_1,\ldots,\vec{v}_k\}$ always a subspace of $V$?
A: It contains $\vec{0}$ (take all $c_i=0$), the sum of two linear combinations is a linear combination, and a scalar times a linear combination is a linear combination. So all three subspace conditions hold automatically.

Q: Geometrically, what is $\text{span}\{\vec{v}\}$ for a single nonzero vector $\vec{v}\in\mathbb{R}^3$?
A: The line through the origin in the direction of $\vec{v}$ — the set of all scalar multiples $c\vec{v}$.

Q: Geometrically, what is $\text{span}\{\vec{u},\vec{v}\}$ for two non-parallel vectors in $\mathbb{R}^3$?
A: The plane through the origin containing both $\vec{u}$ and $\vec{v}$. If $\vec{u}$ and $\vec{v}$ were parallel, the span would collapse to a line.

C: The span of a set $S\subseteq V$ is the [smallest subspace] of $V$ containing $S$.

## 4.7 Null Space

C: The null space of an $m\times n$ matrix $A$ is $\text{Nul}(A) = \{\vec{x}\in\mathbb{R}^n : [A\vec{x}=\vec{0}]\}$, where $\vec{x}$ is an $n$-vector and $\vec{0}$ is the zero vector in $\mathbb{R}^m$.

Q: Why is $\text{Nul}(A)$ a subspace of $\mathbb{R}^n$?
A: It contains $\vec{0}$ because $A\vec{0}=\vec{0}$. If $A\vec{x}=\vec{0}$ and $A\vec{y}=\vec{0}$, then $A(\vec{x}+\vec{y})=\vec{0}$ and $A(c\vec{x})=\vec{0}$ by linearity of matrix multiplication. So all three subspace conditions are inherited from the linearity of $A$.

Q: For an $m\times n$ matrix $A$, is $\text{Nul}(A)$ a subspace of $\mathbb{R}^n$ or $\mathbb{R}^m$, and why?
A: It lives in $\mathbb{R}^n$, because $\vec{x}$ has $n$ components (it must be compatible with the $n$ columns of $A$). The image vector $A\vec{x}$ lives in $\mathbb{R}^m$, but $\vec{x}$ itself does not.

C: Elements of $\text{Nul}(A)$ are precisely the solutions of the [homogeneous system] $A\vec{x}=\vec{0}$.

## 4.8 Column Space

C: The column space of an $m\times n$ matrix $A$, denoted $\text{Col}(A)$, is the [span of the columns of $A$].

Q: For an $m\times n$ matrix $A$, why is $\text{Col}(A)$ a subspace of $\mathbb{R}^m$ (not $\mathbb{R}^n$)?
A: Each column of $A$ is a vector in $\mathbb{R}^m$ (it has $m$ entries). The column space is the span of these $m$-vectors, so it is a subspace of $\mathbb{R}^m$. The number $n$ only counts how many spanning vectors we start with.

Q: What is another way to describe $\text{Col}(A)$ in terms of the map $\vec{x}\mapsto A\vec{x}$?
A: $\text{Col}(A)$ is exactly the set of all possible outputs $A\vec{x}$ as $\vec{x}$ ranges over $\mathbb{R}^n$ — the image (range) of the linear map defined by $A$.

## 4.9 Row Space

C: The row space of $A$, denoted $\text{Row}(A)$, is the [span of the rows of $A$], viewed as vectors in $\mathbb{R}^n$ where $n$ is the number of columns of $A$.

Q: For an $m\times n$ matrix $A$, is $\text{Row}(A)$ a subspace of $\mathbb{R}^n$ or $\mathbb{R}^m$, and why?
A: $\mathbb{R}^n$. Each row of $A$ has $n$ entries (one per column), so the rows are vectors in $\mathbb{R}^n$, and their span is a subspace there.

C: The row space of $A$ equals the column space of [$A^T$] (the transpose of $A$).

## 4.10 Consistency of $A\vec{x}=\vec{b}$

Q: Why is $A\vec{x}=\vec{b}$ consistent if and only if $\vec{b}\in\text{Col}(A)$?
A: Writing $A\vec{x}$ as a linear combination of the columns of $A$ (with coefficients $x_1,\ldots,x_n$), a solution exists exactly when $\vec{b}$ can be expressed that way. That is exactly the definition of $\vec{b}$ lying in the span of the columns, i.e. in $\text{Col}(A)$.

C: The system $A\vec{x}=\vec{b}$ has a solution [if and only if] $\vec{b}\in\text{Col}(A)$.

Q: How does the "$\vec{b}\in\text{Col}(A)$" test give geometric meaning to consistency?
A: It says: a linear system is solvable exactly when its right-hand side $\vec{b}$ already lies inside the subspace swept out by the columns of $A$. Inconsistent systems correspond to a $\vec{b}$ that points "outside" that column space.

## 4.11 Finding the Null Space

Q: What is the standard procedure for finding $\text{Nul}(A)$ explicitly?
A: Row reduce $A$ to RREF, identify free variables, express each basic (pivot) variable in terms of the free variables, and write the general solution as a linear combination of vectors — one vector per free variable. Those vectors span $\text{Nul}(A)$.

C: To find $\text{Nul}(A)$, solve the homogeneous system $A\vec{x}=\vec{0}$ and express the solution set as a [span of vectors], one for each free variable.

P: Find the null space of $A = \begin{bmatrix} 1 & 2 & 0 & -1 \\ 0 & 0 & 1 & 2 \end{bmatrix}$, writing $\text{Nul}(A)$ as a span of explicit vectors.

S:
**IDENTIFY**: Find all $\vec{x}\in\mathbb{R}^4$ with $A\vec{x}=\vec{0}$, then write the solution set as $\text{span}\{\ldots\}$.

**PLAN**:
- $A$ is already in RREF: pivots in columns 1 and 3.
- Free variables: $x_2, x_4$ (non-pivot columns).
- Basic variables $x_1, x_3$ are determined by the free ones via the row equations.
- Write $\vec{x}$ as a linear combination with $x_2$ and $x_4$ as coefficients.

**EXECUTE**:
1. Row 1: $x_1 + 2x_2 - x_4 = 0 \Rightarrow x_1 = -2x_2 + x_4$.
2. Row 2: $x_3 + 2x_4 = 0 \Rightarrow x_3 = -2x_4$.
3. Let $x_2 = s$ and $x_4 = t$ (free parameters). Then
$$\vec{x} = \begin{bmatrix} -2s + t \\ s \\ -2t \\ t \end{bmatrix} = s\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + t\begin{bmatrix} 1 \\ 0 \\ -2 \\ 1 \end{bmatrix}.$$
4. Therefore
$$\text{Nul}(A) = \text{span}\left\{\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix},\ \begin{bmatrix} 1 \\ 0 \\ -2 \\ 1 \end{bmatrix}\right\}.$$

**EVALUATE**:
- Two free variables $\Rightarrow$ two spanning vectors. This matches the rule "(# free vars) = dimension of $\text{Nul}(A)$".
- Check: $A\begin{bmatrix}-2\\1\\0\\0\end{bmatrix} = \begin{bmatrix}-2+2\\0\end{bmatrix}=\vec{0}$ and $A\begin{bmatrix}1\\0\\-2\\1\end{bmatrix} = \begin{bmatrix}1-1\\-2+2\end{bmatrix}=\vec{0}$. ✓

## 4.12 Finding the Column Space

C: A basis for $\text{Col}(A)$ is given by the [pivot columns of $A$] — taken from the original matrix, NOT from its RREF.

Q: Why do the pivot columns of the original $A$ (not RREF) give a basis for $\text{Col}(A)$?
A: Row operations change the columns themselves, so columns of RREF generally span a DIFFERENT subspace than columns of $A$. However, row operations preserve linear dependence relations among columns, so whichever columns are pivots in RREF correspond to linearly independent columns in $A$ — those are a basis for $\text{Col}(A)$.

Q: If the RREF of $A$ has pivots in columns 1 and 3, which columns of $A$ form a basis for $\text{Col}(A)$?
A: The first and third columns of $A$ itself. You use RREF only to locate which column indices are pivots; the actual basis vectors come from the original matrix $A$.

## 4.13 Effect of Row Operations on Spaces

Q: Why do row operations preserve $\text{Nul}(A)$?
A: Row operations produce a matrix $A'$ whose homogeneous system $A'\vec{x}=\vec{0}$ has exactly the same solution set as $A\vec{x}=\vec{0}$. Since $\text{Nul}$ is defined as that solution set, it is unchanged.

Q: Why do row operations preserve $\text{Row}(A)$?
A: Each row operation replaces a row by a linear combination of rows, so the span of the rows (the row space) does not change. The individual rows change, but their span is invariant.

Q: Why do row operations generally NOT preserve $\text{Col}(A)$?
A: Row operations mix entries across rows, which alters each column as a vector in $\mathbb{R}^m$. The new columns span a different subspace in general, even though they share the same dependence pattern as the original columns.

Q: Give a small example where $\text{Col}(A)\ne\text{Col}(\text{RREF}(A))$.
A: Take $A=\begin{bmatrix}1\\1\end{bmatrix}$. Then $\text{Col}(A)=\text{span}\{(1,1)^T\}$ (the line $y=x$). Its RREF is $\begin{bmatrix}1\\0\end{bmatrix}$, whose column space is $\text{span}\{(1,0)^T\}$ (the $x$-axis). These are different lines in $\mathbb{R}^2$, so row reduction changed the column space.

C: Row operations preserve $\text{Nul}(A)$ and $\text{Row}(A)$, but [not $\text{Col}(A)$] in general.

Q: Given that row operations preserve $\text{Nul}$ and $\text{Row}$ but not $\text{Col}$, why is this still useful for finding $\text{Col}(A)$?
A: Row reducing $A$ reveals WHICH columns are pivot columns — i.e., which are linearly independent. You then pull those SAME column indices out of the ORIGINAL $A$ to get a basis for $\text{Col}(A)$. The row reduction is a diagnostic tool, not the source of the basis vectors.
