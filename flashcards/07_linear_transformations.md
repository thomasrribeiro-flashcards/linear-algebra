+++
order = 7
tags = ["math", "linear-algebra", "linear-transformations", "kernel", "range", "standard-matrix", "similarity"]
+++

# Linear Algebra — Linear Transformations

## 7.1 Definition of a Linear Transformation

Q: Why do we single out "linear" maps among all possible functions between vector spaces?
A: Linear maps are the maps that respect the two operations that define a vector space: addition and scalar multiplication. Because every vector space is built from these two operations, a map that preserves them preserves all algebraic structure. This makes linear maps both the most common and the most tractable class of functions in linear algebra.

C: A function $T:V\to W$ between vector spaces is called a [linear transformation] if it preserves addition and scalar multiplication.

C: A map $T:V\to W$ is linear if $T(\vec{u}+\vec{v}) = [T(\vec{u}) + T(\vec{v})]$ for all $\vec{u},\vec{v}\in V$.

C: A map $T:V\to W$ is linear if $T(c\vec{v}) = [cT(\vec{v})]$ for every scalar $c$ and every $\vec{v}\in V$.

C: The two defining axioms of linearity can be combined into the single condition $T(a\vec{u}+b\vec{v}) = [aT(\vec{u})+bT(\vec{v})]$ for all scalars $a,b$ and all $\vec{u},\vec{v}\in V$.

Q: What is the domain and codomain of a linear transformation $T:V\to W$?
A: $V$ is the domain (the input space) and $W$ is the codomain (the target space). Both $V$ and $W$ must be vector spaces over the same field, but they need not have the same dimension. The map sends each $\vec{v}\in V$ to a unique $T(\vec{v})\in W$.

## 7.2 Why Linearity Matters

Q: Why is a linear transformation completely determined by its action on a basis?
A: Every vector $\vec{v}\in V$ can be written uniquely as a linear combination of basis vectors. Because $T$ respects addition and scalar multiplication, knowing $T$ on the basis lets you compute $T(\vec{v})$ for any input. This is why specifying $T(\vec{e}_1),\dots,T(\vec{e}_n)$ is enough to define $T$ everywhere.

C: A linear transformation is [fully determined] by its values on a basis of the domain.

Q: What geometric features do linear transformations of $\mathbb{R}^n$ preserve?
A: They send lines through the origin to lines through the origin (or to the zero vector), preserve parallelism of lines, and preserve ratios of lengths along any given line. They do not generally preserve distances, angles, or lines that miss the origin.

C: Linear transformations map [lines through the origin] to lines through the origin (or to $\vec{0}$).

C: Linear transformations preserve [parallelism]: parallel lines remain parallel (or collapse to a point) after being transformed.

## 7.3 Examples of Linear Transformations

Q: Why is rotation about the origin in $\mathbb{R}^2$ linear?
A: Rotating the sum of two vectors gives the same result as rotating each and then adding, and scaling a vector and then rotating is the same as rotating and then scaling. Geometrically, rotation is rigid and origin-fixing, so it commutes with the parallelogram rule and with scalar stretching. Hence both linearity axioms hold.

C: [Rotation] about the origin in $\mathbb{R}^2$ is a linear transformation.

C: [Reflection] across a line through the origin is a linear transformation.

C: Orthogonal [projection] onto a subspace is a linear transformation.

C: Scaling every vector by a fixed factor $c$, i.e. $T(\vec{v}) = c\vec{v}$, is a linear transformation called a [dilation] (or contraction if $|c|<1$).

C: A [shear] transformation in $\mathbb{R}^2$, such as $T(x,y) = (x+ky,\,y)$, is linear, where $k$ is the fixed shear factor.

Q: Why is differentiation $D:P_n\to P_{n-1}$, $D(p) = p'$, a linear transformation on polynomial spaces $P_n$?
A: Differentiation satisfies $(p+q)' = p' + q'$ and $(cp)' = cp'$ for any polynomials $p,q$ and scalar $c$. These are exactly the two axioms of linearity. So $D$ is a linear map from the space of polynomials of degree at most $n$ to those of degree at most $n-1$.

C: On the space of polynomials, [differentiation] $D(p) = p'$ is a linear transformation.

C: On a space of integrable functions, the [integration] map $T(f) = \int_a^x f(t)\,dt$ is a linear transformation.

Q: Give a simple example of a function $\mathbb{R}\to\mathbb{R}$ that is NOT linear as a vector-space map.
A: $f(x) = x+1$ fails because $f(0)=1\ne 0$, and $f(x)=x^2$ fails because $f(x+y)\ne f(x)+f(y)$ in general. In linear algebra, "linear" is stricter than "straight-line graph": it requires the graph to pass through the origin and have no constant term.

## 7.4 Linearity Forces $T(\vec{0}) = \vec{0}$

Q: Why must every linear transformation send $\vec{0}$ to $\vec{0}$?
A: Apply the scaling axiom with $c=0$: $T(\vec{0}) = T(0\cdot\vec{v}) = 0\cdot T(\vec{v}) = \vec{0}$. So the origin of $V$ is always mapped to the origin of $W$. This provides a quick disqualifying check: if $T(\vec{0})\ne\vec{0}$, then $T$ cannot be linear.

C: Every linear transformation $T:V\to W$ satisfies $T(\vec{0}_V) = [\vec{0}_W]$, where $\vec{0}_V$ and $\vec{0}_W$ are the zero vectors of $V$ and $W$.

C: A quick way to rule out linearity: if $T(\vec{0}) \neq [\vec{0}]$, then $T$ is not a linear transformation.

## 7.5 Matrix Transformations

Q: Why is the map $T_A(\vec{x}) = A\vec{x}$ a linear transformation for any $m\times n$ matrix $A$?
A: Matrix-vector multiplication satisfies $A(\vec{x}+\vec{y}) = A\vec{x} + A\vec{y}$ and $A(c\vec{x}) = cA\vec{x}$ by the distributive laws of matrix arithmetic. These are exactly the two linearity axioms. So every matrix induces a linear transformation from $\mathbb{R}^n$ to $\mathbb{R}^m$.

C: For any $m\times n$ matrix $A$, the map $T_A:\mathbb{R}^n\to\mathbb{R}^m$ defined by $T_A(\vec{x}) = [A\vec{x}]$ is a linear transformation.

Q: Why is EVERY linear map $T:\mathbb{R}^n\to\mathbb{R}^m$ a matrix transformation?
A: The standard basis $\vec{e}_1,\dots,\vec{e}_n$ spans $\mathbb{R}^n$, so $T$ is determined by the images $T(\vec{e}_i)$. Placing these images as columns of a matrix $A$ gives $A\vec{x} = T(\vec{x})$ for every $\vec{x}\in\mathbb{R}^n$. Thus the categories "linear map on $\mathbb{R}^n$" and "$m\times n$ matrix" are the same.

C: Every linear transformation $T:\mathbb{R}^n\to\mathbb{R}^m$ equals $T_A$ for a unique $m\times n$ matrix $A$, called the [standard matrix] of $T$.

## 7.6 Standard Matrix of a Linear Transformation

Q: Why are the columns of the standard matrix of $T:\mathbb{R}^n\to\mathbb{R}^m$ exactly $T(\vec{e}_1),\dots,T(\vec{e}_n)$?
A: Because $A\vec{e}_i$ picks out the $i$-th column of $A$. Setting $A\vec{e}_i = T(\vec{e}_i)$ forces the $i$-th column to be $T(\vec{e}_i)$. Linearity then extends the agreement to every input vector.

C: The standard matrix of a linear transformation $T:\mathbb{R}^n\to\mathbb{R}^m$ has $i$-th column equal to [$T(\vec{e}_i)$], where $\vec{e}_i$ is the $i$-th standard basis vector of $\mathbb{R}^n$.

C: If $A$ is the standard matrix of $T$, then $A = [\,T(\vec{e}_1)\ \mid\ T(\vec{e}_2)\ \mid\ \cdots\ \mid\ T(\vec{e}_n)\,]$, and $T(\vec{x}) = [A\vec{x}]$ for all $\vec{x}$.

## 7.7 Computing Standard Matrices

Q: Anticipation: before deriving it, predict the $2\times 2$ standard matrix for rotation by angle $\theta$ counterclockwise. What should its first column be?
A: The first column is $T(\vec{e}_1)$, the image of $(1,0)$ after rotating by $\theta$, which is $(\cos\theta,\sin\theta)$. This sets up the full matrix: the second column will be the image of $(0,1)$.

C: The standard matrix of counterclockwise rotation by $\theta$ in $\mathbb{R}^2$ is $\begin{pmatrix}\cos\theta & -\sin\theta\\ \sin\theta & \cos\theta\end{pmatrix}$, whose first column $[\begin{pmatrix}\cos\theta\\ \sin\theta\end{pmatrix}]$ is the image of $\vec{e}_1 = (1,0)$.

C: The second column of the $\theta$-rotation matrix is $[\begin{pmatrix}-\sin\theta\\ \cos\theta\end{pmatrix}]$, which is the image of $\vec{e}_2 = (0,1)$.

C: The standard matrix of reflection across the line $y=x$ in $\mathbb{R}^2$ is $[\begin{pmatrix}0 & 1\\ 1 & 0\end{pmatrix}]$, because it swaps the coordinates $(x,y)\mapsto(y,x)$.

C: The standard matrix of reflection across the $x$-axis in $\mathbb{R}^2$ is $[\begin{pmatrix}1 & 0\\ 0 & -1\end{pmatrix}]$, where $x$ is unchanged and $y$ is negated.

C: The standard matrix of scaling by factor $c$ in $\mathbb{R}^n$ is the scalar matrix $[cI_n]$, where $I_n$ is the $n\times n$ identity.

## 7.8 Kernel of a Linear Transformation

Q: Why is the kernel of a linear transformation a subspace of the domain?
A: The kernel contains $\vec{0}$ since $T(\vec{0})=\vec{0}$. If $T(\vec{u})=T(\vec{v})=\vec{0}$, linearity gives $T(\vec{u}+\vec{v})=\vec{0}$ and $T(c\vec{u})=\vec{0}$, so the kernel is closed under addition and scalar multiplication. Hence it satisfies the three subspace axioms.

C: The [kernel] of a linear transformation $T:V\to W$ is $\ker T = \{\vec{v}\in V : T(\vec{v})=\vec{0}_W\}$.

C: The kernel of a linear transformation $T:V\to W$ is always a [subspace] of the domain $V$.

C: For a matrix transformation $T_A(\vec{x})=A\vec{x}$, the kernel of $T_A$ equals the [null space] of the matrix $A$.

## 7.9 Range of a Linear Transformation

Q: Why is the range (image) of a linear transformation a subspace of the codomain?
A: The range contains $\vec{0}_W = T(\vec{0}_V)$. If $\vec{w}_1 = T(\vec{v}_1)$ and $\vec{w}_2 = T(\vec{v}_2)$ are in the range, then $\vec{w}_1+\vec{w}_2 = T(\vec{v}_1+\vec{v}_2)$ and $c\vec{w}_1 = T(c\vec{v}_1)$ are too. So the range is closed under the vector-space operations.

C: The [range] (or image) of $T:V\to W$ is $T(V) = \{T(\vec{v}) : \vec{v}\in V\}\subseteq W$.

C: The range of a linear transformation $T:V\to W$ is always a [subspace] of the codomain $W$.

C: For a matrix transformation $T_A$, the range of $T_A$ equals the [column space] of the matrix $A$.

## 7.10 Injectivity and the Kernel

Q: Why is a linear transformation one-to-one if and only if its kernel is trivial?
A: If $T(\vec{u})=T(\vec{v})$, then by linearity $T(\vec{u}-\vec{v})=\vec{0}$, so $\vec{u}-\vec{v}\in\ker T$. If $\ker T=\{\vec{0}\}$, this forces $\vec{u}=\vec{v}$, i.e. injectivity. Conversely, if $T$ is injective, only $\vec{0}$ can map to $\vec{0}$, so $\ker T=\{\vec{0}\}$.

C: A linear transformation $T:V\to W$ is [one-to-one] (injective) if and only if $\ker T = \{\vec{0}\}$.

C: A linear map with nontrivial kernel collapses a whole subspace to $\vec{0}$ and therefore cannot be [injective].

## 7.11 Surjectivity and the Range

Q: What does it mean for a linear transformation $T:V\to W$ to be onto?
A: It means every $\vec{w}\in W$ is the image of some $\vec{v}\in V$. Equivalently, the range $T(V)$ equals the entire codomain $W$. For matrix transformations $T_A:\mathbb{R}^n\to\mathbb{R}^m$, this is equivalent to the column space of $A$ being all of $\mathbb{R}^m$, i.e. $\operatorname{rank}(A)=m$.

C: A linear transformation $T:V\to W$ is [onto] (surjective) if and only if its range equals $W$.

C: A matrix transformation $T_A:\mathbb{R}^n\to\mathbb{R}^m$ is onto iff the rank of $A$ equals $[m]$, the dimension of the codomain.

## 7.12 Rank-Nullity for Linear Transformations

Q: Why does rank-nullity ($\dim\ker T + \dim\operatorname{range}(T) = \dim V$) hold for linear transformations, not just matrices?
A: Choose a basis for $\ker T$ and extend it to a basis of $V$. The extended vectors map to a basis of the range, because their images are linearly independent and span $T(V)$. Counting basis sizes on both sides gives $\dim V = \dim\ker T + \dim\operatorname{range}(T)$.

C: The rank-nullity theorem for a linear transformation $T:V\to W$ states $\dim\ker T + \dim\operatorname{range}(T) = [\dim V]$, the dimension of the domain.

C: In matrix language, rank-nullity says $\operatorname{rank}(A) + \operatorname{nullity}(A) = [n]$, the number of columns of $A$.

Q: If $T:V\to W$ is a linear map with $\dim V > \dim W$, why can $T$ never be injective?
A: By rank-nullity, $\dim\ker T = \dim V - \dim\operatorname{range}(T) \ge \dim V - \dim W > 0$. A positive-dimensional kernel means there is a nonzero vector mapped to $\vec{0}$, so $T$ is not one-to-one. Intuitively, you cannot squeeze a higher-dimensional space injectively into a lower-dimensional one.

Q: If $T:V\to W$ is a linear map with $\dim V < \dim W$, why can $T$ never be surjective?
A: By rank-nullity, $\dim\operatorname{range}(T)\le\dim V<\dim W$. So the range is a proper subspace of $W$ and cannot be all of $W$. Intuitively, the image of a lower-dimensional space is too small to fill a higher-dimensional codomain.

## 7.13 Matrix of a Linear Transformation Between General Vector Spaces

Q: Why can every linear transformation between finite-dimensional vector spaces be represented by a matrix, once bases are chosen?
A: Choosing bases for $V$ and $W$ gives coordinate isomorphisms with $\mathbb{R}^n$ and $\mathbb{R}^m$. Under these coordinates, $T$ becomes a linear map $\mathbb{R}^n\to\mathbb{R}^m$, which must be a matrix transformation. The matrix entries record how $T$ sends each domain basis vector, expressed in coordinates over the codomain basis.

C: Given a basis $\mathcal{B}=\{\vec{v}_1,\dots,\vec{v}_n\}$ of $V$ and a basis $\mathcal{C}$ of $W$, the [matrix of $T$ with respect to $\mathcal{B}$ and $\mathcal{C}$], denoted $[T]_{\mathcal{C}\leftarrow\mathcal{B}}$, has $i$-th column equal to $[T(\vec{v}_i)]_{\mathcal{C}}$, the $\mathcal{C}$-coordinates of $T(\vec{v}_i)$.

C: Under the matrix representation, coordinates transform by $[T(\vec{v})]_{\mathcal{C}} = [\,[T]_{\mathcal{C}\leftarrow\mathcal{B}}\cdot[\vec{v}]_{\mathcal{B}}\,]$, where $[\vec{v}]_{\mathcal{B}}$ is the coordinate vector of $\vec{v}$ in basis $\mathcal{B}$.

Q: Why does the matrix of a linear transformation depend on the choice of bases?
A: The matrix records how basis vectors map to coordinates of other basis vectors. Changing either basis changes which vectors serve as reference directions and therefore changes the numerical entries. The underlying transformation is unchanged, but its numerical description is basis-dependent.

## 7.14 Composition and Matrix Multiplication

Q: Why does matrix multiplication correspond to composition of linear transformations?
A: If $S:U\to V$ has matrix $B$ and $T:V\to W$ has matrix $A$, then $(T\circ S)(\vec{x}) = T(S(\vec{x})) = A(B\vec{x}) = (AB)\vec{x}$. So the composition's matrix is the product $AB$. Matrix multiplication was in fact defined precisely so this relationship holds.

C: If $S:U\to V$ and $T:V\to W$ are linear maps with matrices $B$ and $A$ in chosen bases, then the composition $T\circ S$ has matrix $[AB]$.

C: Composition of linear transformations is [associative] because matrix multiplication is: $(T\circ S)\circ R = T\circ(S\circ R)$.

Q: Why is composition of linear transformations generally not commutative?
A: Matrix multiplication is generally noncommutative: $AB\ne BA$ in general. Geometrically, "rotate then reflect" is not the same as "reflect then rotate." So swapping the order of composed linear maps usually changes the result.

## 7.15 Isomorphism

Q: What is an isomorphism of vector spaces, and why is it the "right" notion of sameness?
A: An isomorphism is a bijective linear map $T:V\to W$. It preserves all algebraic structure (addition, scalar multiplication) AND pairs the vectors of $V$ and $W$ one-to-one. Two vector spaces related by an isomorphism are indistinguishable as vector spaces: any statement true in one, expressible with the vector-space operations, is true in the other.

C: An [isomorphism] is a linear transformation that is both one-to-one and onto (i.e. bijective).

C: Two vector spaces $V$ and $W$ are called [isomorphic], written $V\cong W$, if there exists an isomorphism $T:V\to W$.

Q: Why is a linear map between finite-dimensional spaces of the same dimension injective iff surjective iff an isomorphism?
A: By rank-nullity, if $\dim V = \dim W = n$, then $\dim\ker T + \dim\operatorname{range}(T) = n$. Injectivity ($\dim\ker T=0$) forces $\dim\operatorname{range}(T)=n=\dim W$, giving surjectivity. The converse is identical. So in equal finite dimensions, each of the three conditions implies the others.

C: For a linear map $T:V\to W$ between finite-dimensional spaces of the [same dimension], injectivity, surjectivity, and invertibility are all equivalent.

C: A square matrix $A$ represents an isomorphism of $\mathbb{R}^n$ if and only if $A$ is [invertible] (equivalently, $\det A\ne 0$).

Q: Why are all $n$-dimensional real vector spaces isomorphic to $\mathbb{R}^n$?
A: Choosing a basis $\mathcal{B}$ of an $n$-dimensional space $V$ defines a coordinate map $[\cdot]_{\mathcal{B}}:V\to\mathbb{R}^n$ that is linear and bijective. So any two vector spaces with the same finite dimension are isomorphic via their coordinate maps. This is why dimension is the only invariant of finite-dimensional vector spaces.

## 7.16 Similar Matrices

Q: Why do similar matrices $B=P^{-1}AP$ represent the same linear transformation?
A: If $A$ is the matrix of $T$ in basis $\mathcal{B}$ and $P$ is the change-of-basis matrix from $\mathcal{B}'$ to $\mathcal{B}$, then in basis $\mathcal{B}'$ the same transformation has matrix $P^{-1}AP$. The matrix changes because coordinates change, but the underlying geometric action on vectors is identical.

C: Two square matrices $A$ and $B$ are [similar], written $A\sim B$, if there exists an invertible matrix $P$ with $B = P^{-1}AP$.

C: Similar matrices represent the [same linear transformation] in different bases, where $P$ is the change-of-basis matrix.

C: Similarity is an [equivalence relation]: reflexive ($A=I^{-1}AI$), symmetric, and transitive.

Q: Which properties of a matrix are invariant under similarity, and why?
A: Because similar matrices describe the same transformation, any property intrinsic to the transformation is shared. These include determinant, trace, rank, nullity, characteristic polynomial, and eigenvalues. Basis-dependent features like individual entries are not preserved.

C: Invariants under similarity include [determinant], trace, rank, characteristic polynomial, and eigenvalues.

## 7.17 Finding the Matrix of a Transformation

P: A linear transformation $T:\mathbb{R}^3\to\mathbb{R}^2$ satisfies $T(1,0,0)=(2,1)$, $T(0,1,0)=(-1,3)$, and $T(0,0,1)=(4,0)$. Find the standard matrix of $T$ and compute $T(1,2,-1)$.

S:
**IDENTIFY**: Standard-matrix construction for a linear map $\mathbb{R}^3\to\mathbb{R}^2$ given its action on the three standard basis vectors $\vec{e}_1,\vec{e}_2,\vec{e}_3$, followed by a coordinate evaluation.

**PLAN**:
- Use the fact that the standard matrix $A$ of $T$ has $T(\vec{e}_i)$ as its $i$-th column.
- Assemble $A$ as a $2\times 3$ matrix from the three given images.
- Compute $T(\vec{x})$ for $\vec{x}=(1,2,-1)$ via $A\vec{x}$.

**EXECUTE**:
1. Column 1 of $A$ is $T(\vec{e}_1) = (2,1)$.
2. Column 2 of $A$ is $T(\vec{e}_2) = (-1,3)$.
3. Column 3 of $A$ is $T(\vec{e}_3) = (4,0)$.
4. So $A = \begin{pmatrix}2 & -1 & 4\\ 1 & 3 & 0\end{pmatrix}$.
5. Compute $T(1,2,-1) = A\begin{pmatrix}1\\ 2\\ -1\end{pmatrix} = \begin{pmatrix}2(1)+(-1)(2)+4(-1)\\ 1(1)+3(2)+0(-1)\end{pmatrix} = \begin{pmatrix}-4\\ 7\end{pmatrix}$.

**EVALUATE**:
- Cross-check via linearity: $T(1,2,-1) = T(\vec{e}_1) + 2T(\vec{e}_2) - T(\vec{e}_3) = (2,1) + 2(-1,3) - (4,0) = (2-2-4,\,1+6-0) = (-4,7)$. Matches.
- Dimensions are consistent: $A$ is $2\times 3$, input is $3\times 1$, output is $2\times 1$.
- The matrix is the unique standard matrix of $T$, since every linear map $\mathbb{R}^3\to\mathbb{R}^2$ is represented by a unique $2\times 3$ matrix.
