+++
order = 9
subject = "Mathematics"
tags = ["math", "linear-algebra", "inner-product", "orthogonality", "projection", "orthogonal-basis", "orthogonal-complement"]
+++

# Linear Algebra — Inner Products and Orthogonality

## 9.1 Dot Product in $\mathbb{R}^n$

Q: Why do we introduce the dot product on $\mathbb{R}^n$?
A: Vector spaces by themselves have no notion of length or angle — they only capture linear combinations. The dot product adds a geometric structure on top, giving us a way to measure size, distance, and perpendicularity using coordinates. It is the bridge between algebra (coordinate sums) and geometry (lengths and angles).

C: The [dot product] of $\vec{u}, \vec{v} \in \mathbb{R}^n$ is defined by $\vec{u}\cdot\vec{v} = \sum_{i=1}^n u_i v_i$, where $u_i$ and $v_i$ are the $i$th components.

C: Written as a matrix product, $\vec{u}\cdot\vec{v} = [\vec{u}^T\vec{v}]$, where $\vec{u}, \vec{v}$ are column vectors in $\mathbb{R}^n$.

Q: What type of object is $\vec{u}\cdot\vec{v}$?
A: A scalar (a single real number), not a vector. Even though we combine two vectors, the sum of products collapses to one number, which is exactly what we need to measure length and angle.

C: The dot product is symmetric: $\vec{u}\cdot\vec{v} = [\vec{v}\cdot\vec{u}]$, where $\vec{u}, \vec{v} \in \mathbb{R}^n$.

C: The dot product is linear in each argument: $(a\vec{u} + b\vec{w})\cdot\vec{v} = [a(\vec{u}\cdot\vec{v}) + b(\vec{w}\cdot\vec{v})]$, where $a, b$ are scalars.

C: For any $\vec{v} \in \mathbb{R}^n$, $\vec{v}\cdot\vec{v} \geq [0]$, with equality if and only if $\vec{v} = \vec{0}$.

## 9.2 Length (Norm)

Q: Why is the length of $\vec{v}$ defined as $\sqrt{\vec{v}\cdot\vec{v}}$?
A: In $\mathbb{R}^2$ and $\mathbb{R}^3$, the Pythagorean theorem gives length as $\sqrt{v_1^2 + \cdots + v_n^2}$, and this is exactly $\sqrt{\vec{v}\cdot\vec{v}}$. Extending this to $\mathbb{R}^n$ defines length in any dimension in a way that matches our geometric intuition in low dimensions.

C: The [norm] (length) of $\vec{v} \in \mathbb{R}^n$ is $\|\vec{v}\| = \sqrt{\vec{v}\cdot\vec{v}}$.

C: Expanding the norm in coordinates, $\|\vec{v}\| = [\sqrt{v_1^2 + v_2^2 + \cdots + v_n^2}]$, where $v_i$ is the $i$th component of $\vec{v}$.

C: Scaling a vector scales its length: $\|c\vec{v}\| = [|c|\,\|\vec{v}\|]$, where $c$ is a scalar and $\vec{v} \in \mathbb{R}^n$.

C: A useful identity: $\|\vec{v}\|^2 = [\vec{v}\cdot\vec{v}]$, letting us avoid square roots in proofs.

## 9.3 Unit Vector

Q: Why normalize a vector to unit length?
A: A unit vector captures only the direction of a vector, stripping away magnitude. This is useful for expressing pure directions (e.g., basis vectors, projections) and for comparing orientations independent of scale.

C: A [unit vector] is a vector $\vec{v}$ with $\|\vec{v}\| = 1$.

C: To normalize $\vec{v} \neq \vec{0}$, compute $\hat{v} = [\vec{v}/\|\vec{v}\|]$, which has length $1$ and the same direction as $\vec{v}$.

Q: Why does $\vec{v}/\|\vec{v}\|$ have length $1$?
A: By the scaling rule, $\|c\vec{v}\| = |c|\,\|\vec{v}\|$. Taking $c = 1/\|\vec{v}\|$ gives length $(1/\|\vec{v}\|)\cdot\|\vec{v}\| = 1$. So dividing by the length rescales to length $1$.

## 9.4 Distance

Q: Why define distance between $\vec{u}$ and $\vec{v}$ as $\|\vec{u}-\vec{v}\|$?
A: The vector $\vec{u}-\vec{v}$ points from $\vec{v}$ to $\vec{u}$, and its length is the geometric gap between the two points. This generalizes the Euclidean distance formula in $\mathbb{R}^2$ and $\mathbb{R}^3$ to any dimension.

C: The [distance] between $\vec{u}, \vec{v} \in \mathbb{R}^n$ is $\text{dist}(\vec{u}, \vec{v}) = \|\vec{u} - \vec{v}\|$.

C: Distance is symmetric: $\text{dist}(\vec{u}, \vec{v}) = [\text{dist}(\vec{v}, \vec{u})]$, since $\|\vec{u} - \vec{v}\| = \|-(\vec{v}-\vec{u})\| = \|\vec{v}-\vec{u}\|$.

## 9.5 Orthogonality

Q: Why is the algebraic condition $\vec{u}\cdot\vec{v} = 0$ the right definition of "perpendicular"?
A: In $\mathbb{R}^2$ and $\mathbb{R}^3$, the law of cosines gives $\vec{u}\cdot\vec{v} = \|\vec{u}\|\,\|\vec{v}\|\cos\theta$, where $\theta$ is the angle between $\vec{u}$ and $\vec{v}$. So $\vec{u}\cdot\vec{v} = 0$ iff $\cos\theta = 0$ iff $\theta = 90^\circ$. Extending this condition to $\mathbb{R}^n$ defines perpendicularity in dimensions where we cannot "see" angles.

C: Two vectors $\vec{u}, \vec{v} \in \mathbb{R}^n$ are [orthogonal] if $\vec{u}\cdot\vec{v} = 0$.

C: The zero vector is orthogonal to [every] vector in $\mathbb{R}^n$, since $\vec{0}\cdot\vec{v} = 0$ for all $\vec{v}$.

Q: Why is orthogonality a symmetric relation?
A: Since $\vec{u}\cdot\vec{v} = \vec{v}\cdot\vec{u}$, if $\vec{u}\perp\vec{v}$ then $\vec{v}\perp\vec{u}$. The dot product being symmetric makes "perpendicular" a symmetric notion, matching geometric intuition.

## 9.6 Pythagorean Theorem

Q: Why does $\|\vec{u}+\vec{v}\|^2 = \|\vec{u}\|^2 + \|\vec{v}\|^2$ characterize orthogonality?
A: Expanding, $\|\vec{u}+\vec{v}\|^2 = (\vec{u}+\vec{v})\cdot(\vec{u}+\vec{v}) = \|\vec{u}\|^2 + 2\vec{u}\cdot\vec{v} + \|\vec{v}\|^2$. The "cross term" $2\vec{u}\cdot\vec{v}$ vanishes exactly when $\vec{u}\cdot\vec{v} = 0$, which is the definition of orthogonality. So Pythagoras holds iff the vectors are orthogonal.

C: Pythagorean theorem (in $\mathbb{R}^n$): $\|\vec{u}+\vec{v}\|^2 = \|\vec{u}\|^2 + \|\vec{v}\|^2$ iff $[\vec{u}\cdot\vec{v} = 0]$ (i.e., $\vec{u}\perp\vec{v}$).

## 9.7 Orthogonal Complement

Q: Why is it useful to talk about the set of all vectors orthogonal to a subspace?
A: Many problems split naturally into "components along $W$" and "components perpendicular to $W$" — projections, least-squares, and fundamental-subspace decompositions all rely on this split. The orthogonal complement packages "everything perpendicular to $W$" as its own subspace, letting us manipulate it algebraically.

C: Given a subspace $W \subseteq \mathbb{R}^n$, the [orthogonal complement] $W^\perp$ is the set of all $\vec{v} \in \mathbb{R}^n$ with $\vec{v}\cdot\vec{w} = 0$ for every $\vec{w} \in W$.

Q: Why is $W^\perp$ itself a subspace of $\mathbb{R}^n$?
A: It contains $\vec{0}$ (since $\vec{0}\cdot\vec{w}=0$), and if $\vec{u}, \vec{v} \in W^\perp$ and $c$ is a scalar, then $(\vec{u}+c\vec{v})\cdot\vec{w} = \vec{u}\cdot\vec{w} + c(\vec{v}\cdot\vec{w}) = 0$ for all $\vec{w} \in W$, by linearity of the dot product. So $W^\perp$ is closed under addition and scalar multiplication.

C: To check $\vec{v} \in W^\perp$, it suffices to verify $\vec{v}\cdot\vec{w}_i = 0$ for every vector $\vec{w}_i$ in a [spanning set / basis] of $W$, because orthogonality extends linearly.

C: For any subspace $W \subseteq \mathbb{R}^n$, $\dim W + \dim W^\perp = [n]$, so the two subspaces together fill up $\mathbb{R}^n$.

## 9.8 Fundamental Subspaces and Orthogonal Complements

Q: Why is $\text{Row}(A)^\perp = \text{Nul}(A)$?
A: A vector $\vec{x}$ lies in $\text{Nul}(A)$ iff $A\vec{x} = \vec{0}$, which means each row of $A$ dotted with $\vec{x}$ is zero. That is exactly the condition that $\vec{x}$ is orthogonal to every row, i.e., to all of $\text{Row}(A)$. So the null space is precisely the orthogonal complement of the row space.

C: For any matrix $A$, $\text{Row}(A)^\perp = [\text{Nul}(A)]$, where $\text{Nul}(A)$ is the null space of $A$.

C: For any matrix $A$, $\text{Col}(A)^\perp = [\text{Nul}(A^T)]$, since the columns of $A$ are the rows of $A^T$.

Q: How do these relations reveal a dimension count?
A: Combining $\dim\text{Row}(A) + \dim\text{Nul}(A) = n$ (rank-nullity) with $\text{Row}(A)^\perp = \text{Nul}(A)$ shows that row space and null space are orthogonal complements in $\mathbb{R}^n$. Likewise $\text{Col}(A)$ and $\text{Nul}(A^T)$ are orthogonal complements in $\mathbb{R}^m$, giving the full four-fundamental-subspaces picture.

## 9.9 Orthogonal Sets

Q: Why are orthogonal sets of nonzero vectors always linearly independent?
A: Suppose $c_1\vec{v}_1 + \cdots + c_k\vec{v}_k = \vec{0}$ for an orthogonal set $\{\vec{v}_1,\dots,\vec{v}_k\}$. Taking the dot product with $\vec{v}_i$ makes every term vanish except $c_i(\vec{v}_i\cdot\vec{v}_i)$. Since $\vec{v}_i \neq \vec{0}$, $\vec{v}_i\cdot\vec{v}_i > 0$, forcing $c_i = 0$. So the only linear combination giving zero is trivial — independence.

C: An [orthogonal set] is a set of nonzero vectors $\{\vec{v}_1, \dots, \vec{v}_k\}$ with $\vec{v}_i\cdot\vec{v}_j = 0$ whenever $i \neq j$.

C: Every orthogonal set of nonzero vectors is [linearly independent].

Q: Why does the orthogonal set definition require nonzero vectors?
A: The zero vector is orthogonal to everything, so including it would make the "pairwise orthogonal" condition trivially true but break linear independence (since $\vec{0}$ is dependent on anything). Excluding zero keeps the useful property that orthogonality implies independence.

## 9.10 Orthogonal Basis

Q: Why is an orthogonal basis more convenient than a general basis?
A: In a general basis, finding coordinates of $\vec{x}$ requires solving a linear system $B\vec{c} = \vec{x}$. In an orthogonal basis, the basis vectors don't interfere with each other under the dot product, so each coordinate can be read off independently via a single dot product — no system to solve.

C: An [orthogonal basis] of a subspace $W$ is a basis $\{\vec{b}_1, \dots, \vec{b}_k\}$ of $W$ that is also an orthogonal set.

## 9.11 Coordinates in an Orthogonal Basis

Q: Why does $c_i = \frac{\vec{x}\cdot\vec{b}_i}{\vec{b}_i\cdot\vec{b}_i}$ give the $i$th coordinate of $\vec{x}$?
A: Write $\vec{x} = c_1\vec{b}_1 + \cdots + c_k\vec{b}_k$. Dot both sides with $\vec{b}_i$: orthogonality kills every term except $c_i(\vec{b}_i\cdot\vec{b}_i)$, giving $\vec{x}\cdot\vec{b}_i = c_i(\vec{b}_i\cdot\vec{b}_i)$. Solving isolates $c_i$. Orthogonality decouples the coordinates.

C: If $\{\vec{b}_1,\dots,\vec{b}_k\}$ is an orthogonal basis of $W$ and $\vec{x} \in W$, then $\vec{x} = \sum_i c_i \vec{b}_i$ with $c_i = [\frac{\vec{x}\cdot\vec{b}_i}{\vec{b}_i\cdot\vec{b}_i}]$.

Q: What fails if the basis is not orthogonal?
A: The cross-terms $c_j(\vec{b}_j\cdot\vec{b}_i)$ for $j \neq i$ no longer vanish, so a single dot product mixes several coordinates. You must solve the full linear system to recover the $c_i$'s.

## 9.12 Orthonormal Basis

Q: Why is an orthonormal basis even more convenient than merely orthogonal?
A: If each basis vector has length $1$, then $\vec{b}_i\cdot\vec{b}_i = 1$, and the coordinate formula $c_i = (\vec{x}\cdot\vec{b}_i)/(\vec{b}_i\cdot\vec{b}_i)$ collapses to $c_i = \vec{x}\cdot\vec{b}_i$. No division is needed; coordinates are just dot products with basis vectors.

C: An [orthonormal basis] is an orthogonal basis in which every vector also has unit length.

C: If $\{\vec{b}_1, \dots, \vec{b}_k\}$ is an orthonormal basis of $W$ and $\vec{x} \in W$, then $c_i = [\vec{x}\cdot\vec{b}_i]$, where $c_i$ is the $i$th coordinate of $\vec{x}$.

C: To convert an orthogonal basis to an orthonormal one, replace each $\vec{b}_i$ by $[\vec{b}_i/\|\vec{b}_i\|]$, the unit vector in its direction.

## 9.13 Orthogonal Matrix

Q: Why call a square matrix with orthonormal columns "orthogonal"?
A: The condition that the columns are orthonormal is equivalent to $U^T U = I$, meaning $U^T$ is the inverse of $U$. The "orthogonal" in the name refers to the columns being pairwise orthogonal (and unit length); the algebraic payoff is that inversion reduces to transposition, which is cheap.

C: A square matrix $U$ is called [orthogonal] if $U^T U = I$, equivalently $U^{-1} = U^T$.

C: The columns of an orthogonal matrix $U$ form an [orthonormal] set (orthonormal basis of $\mathbb{R}^n$).

Q: Why does $U^T U = I$ encode "columns are orthonormal"?
A: The $(i,j)$ entry of $U^T U$ is $\vec{u}_i\cdot\vec{u}_j$, where $\vec{u}_i$ is the $i$th column of $U$. This equals $1$ on the diagonal (unit length) and $0$ off-diagonal (pairwise orthogonal) exactly when the columns form an orthonormal set. So $U^T U = I$ is shorthand for orthonormal columns.

Q: A common pitfall: what does the term "orthogonal matrix" require of the columns, beyond their being pairwise orthogonal?
A: The standard term "orthogonal matrix" requires orthonormal columns (orthogonal AND unit length). A matrix with merely orthogonal (non-unit) columns satisfies $U^T U = D$ for a diagonal $D$, not $I$.

## 9.14 Orthogonal Matrices Preserve Length and Angle

Q: Why do orthogonal matrices preserve lengths?
A: $\|U\vec{x}\|^2 = (U\vec{x})^T(U\vec{x}) = \vec{x}^T U^T U \vec{x} = \vec{x}^T I \vec{x} = \|\vec{x}\|^2$. The $U^T U = I$ property collapses the middle, so $U$ cannot stretch or shrink any vector. Orthogonal matrices act as rigid motions.

C: If $U$ is orthogonal, then $\|U\vec{x}\| = [\|\vec{x}\|]$ for every $\vec{x}$, where $\vec{x}$ is any vector in $\mathbb{R}^n$.

C: If $U$ is orthogonal, then $(U\vec{x})\cdot(U\vec{y}) = [\vec{x}\cdot\vec{y}]$, so $U$ preserves angles as well as lengths.

Q: Geometrically, what kinds of maps do orthogonal matrices represent?
A: Because they preserve lengths and angles (and so shapes), orthogonal matrices represent rigid transformations fixing the origin — rotations and reflections (and their compositions). No stretching, shearing, or distortion is possible.

## 9.15 Orthogonal Projection Onto a Line

Q: Why does the projection of $\vec{x}$ onto the line spanned by $\vec{u}$ equal $\frac{\vec{x}\cdot\vec{u}}{\vec{u}\cdot\vec{u}}\vec{u}$?
A: We want a scalar multiple $c\vec{u}$ of $\vec{u}$ such that $\vec{x} - c\vec{u}$ is orthogonal to $\vec{u}$. Setting $(\vec{x}-c\vec{u})\cdot\vec{u} = 0$ gives $c = (\vec{x}\cdot\vec{u})/(\vec{u}\cdot\vec{u})$. So the projection is the unique multiple of $\vec{u}$ whose error is perpendicular to $\vec{u}$.

C: The [orthogonal projection] of $\vec{x}$ onto the line through $\vec{u} \neq \vec{0}$ is $\text{proj}_{\vec{u}}\vec{x} = \frac{\vec{x}\cdot\vec{u}}{\vec{u}\cdot\vec{u}}\vec{u}$.

C: If $\vec{u}$ is a unit vector, the projection simplifies to $\text{proj}_{\vec{u}}\vec{x} = [(\vec{x}\cdot\vec{u})\vec{u}]$.

Q: What is the geometric meaning of the "residual" $\vec{x} - \text{proj}_{\vec{u}}\vec{x}$?
A: It is the component of $\vec{x}$ perpendicular to $\vec{u}$ — the piece of $\vec{x}$ that has no overlap with the direction of $\vec{u}$. So every $\vec{x}$ splits uniquely as (component along $\vec{u}$) + (component perpendicular to $\vec{u}$).

## 9.16 Orthogonal Projection Onto a Subspace

Q: Why can we project onto a subspace $W$ by summing projections onto each vector of an orthogonal basis?
A: Since the basis is orthogonal, the projections onto different basis vectors don't interfere: the residual from projecting onto $\vec{u}_1$ is already orthogonal to $\vec{u}_1$, and projecting it further onto $\vec{u}_2$ leaves the $\vec{u}_1$-component untouched. Summing the individual projections therefore reconstructs the full component of $\vec{x}$ in $W$.

C: If $\{\vec{u}_1, \dots, \vec{u}_k\}$ is an orthogonal basis of $W$, then $\text{proj}_W\vec{x} = [\sum_{i=1}^k \frac{\vec{x}\cdot\vec{u}_i}{\vec{u}_i\cdot\vec{u}_i}\vec{u}_i]$, where $\vec{x}$ is any vector in $\mathbb{R}^n$.

Q: Why does this formula fail for a non-orthogonal basis?
A: With a non-orthogonal basis, projecting onto $\vec{u}_1$ leaves a residual that is not orthogonal to $\vec{u}_2$, so subsequent projections double-count or under-count components. Cross-terms $\vec{u}_i\cdot\vec{u}_j \neq 0$ couple the coefficients, and you must solve a system (or first orthogonalize, e.g., Gram–Schmidt).

C: The orthogonal decomposition of $\vec{x}$ with respect to $W$ is $\vec{x} = \text{proj}_W\vec{x} + \vec{z}$, where $\vec{z} \in [W^\perp]$.

## 9.17 Best Approximation

Q: Why does $\text{proj}_W\vec{x}$ minimize the distance from $\vec{x}$ to $W$?
A: For any $\vec{w} \in W$, write $\vec{x} - \vec{w} = (\vec{x} - \text{proj}_W\vec{x}) + (\text{proj}_W\vec{x} - \vec{w})$. The first summand lies in $W^\perp$ and the second in $W$, so they are orthogonal. By Pythagoras, $\|\vec{x}-\vec{w}\|^2 = \|\vec{x}-\text{proj}_W\vec{x}\|^2 + \|\text{proj}_W\vec{x}-\vec{w}\|^2$, minimized when the second term is zero, i.e., when $\vec{w} = \text{proj}_W\vec{x}$.

C: [Best approximation theorem]: for any $\vec{x}$ and subspace $W$, $\text{proj}_W\vec{x}$ is the unique vector in $W$ closest to $\vec{x}$.

Q: Where does the best-approximation property show up in applications?
A: Least-squares regression: when $A\vec{c} = \vec{y}$ has no exact solution, we instead solve $A\vec{c} = \text{proj}_{\text{Col}(A)}\vec{y}$, finding the $\vec{c}$ whose prediction is closest (in Euclidean distance) to the observed data $\vec{y}$.

## 9.18 General Inner Products on Vector Spaces

Q: Why generalize the dot product to arbitrary vector spaces?
A: Many useful vector spaces — spaces of functions, polynomials, matrices — have no natural "coordinate sum," but we still want notions of length, angle, orthogonality, and projection. An inner product axiomatizes the essential properties of the dot product so we can transplant geometric ideas (Fourier series, least squares, orthogonality of functions) to these settings.

C: An [inner product] on a real vector space $V$ is a function $\langle\cdot,\cdot\rangle:V\times V\to\mathbb{R}$ that is symmetric, linear in each argument, and positive definite (i.e., $\langle\vec{v},\vec{v}\rangle > 0$ for $\vec{v} \neq \vec{0}$).

C: Symmetry axiom: $\langle\vec{u},\vec{v}\rangle = [\langle\vec{v},\vec{u}\rangle]$, for all $\vec{u}, \vec{v} \in V$.

C: Linearity in the first argument: $\langle a\vec{u}+b\vec{w},\vec{v}\rangle = [a\langle\vec{u},\vec{v}\rangle + b\langle\vec{w},\vec{v}\rangle]$, where $a, b$ are scalars.

C: Positive definiteness: $\langle\vec{v},\vec{v}\rangle \geq 0$, with equality iff $\vec{v} = [\vec{0}]$.

C: On $C[a,b]$ (continuous functions on $[a,b]$), a standard inner product is $\langle f,g\rangle = [\int_a^b f(t)g(t)\,dt]$, where $f, g$ are continuous real-valued functions.

Q: Why does $\langle f,g\rangle = \int_a^b f(t)g(t)\,dt$ satisfy positive definiteness?
A: $\langle f,f\rangle = \int_a^b f(t)^2\,dt \geq 0$ since the integrand is nonnegative. Moreover, for continuous $f$, this integral is zero only if $f(t) \equiv 0$ on $[a,b]$. So nonzero continuous functions have strictly positive self-inner-product, as required.

Q: Given a general inner product, how do we define length and orthogonality?
A: Length is $\|\vec{v}\| = \sqrt{\langle\vec{v},\vec{v}\rangle}$, and two vectors are orthogonal iff $\langle\vec{u},\vec{v}\rangle = 0$. All the theory — Pythagoras, projections, best approximation — carries over verbatim with $\langle\cdot,\cdot\rangle$ replacing $\vec{u}\cdot\vec{v}$.

## 9.19 Cauchy–Schwarz Inequality

Q: Why is the Cauchy–Schwarz inequality important?
A: It guarantees $|\vec{u}\cdot\vec{v}| \leq \|\vec{u}\|\|\vec{v}\|$, which is exactly what allows us to define the angle between any two vectors via $\cos\theta = (\vec{u}\cdot\vec{v})/(\|\vec{u}\|\|\vec{v}\|)$ — the right side is always in $[-1,1]$. It also underlies the triangle inequality and countless estimates throughout analysis.

C: [Cauchy–Schwarz inequality]: for all $\vec{u}, \vec{v}$ in an inner product space, $|\langle\vec{u},\vec{v}\rangle| \leq \|\vec{u}\|\,\|\vec{v}\|$.

C: Equality in Cauchy–Schwarz holds iff $\vec{u}$ and $\vec{v}$ are [linearly dependent] (one is a scalar multiple of the other).

Q: How does Cauchy–Schwarz let us define the angle between vectors in $\mathbb{R}^n$?
A: Rearranging, $-1 \leq (\vec{u}\cdot\vec{v})/(\|\vec{u}\|\|\vec{v}\|) \leq 1$ for nonzero $\vec{u}, \vec{v}$. So there is a unique $\theta \in [0,\pi]$ with $\cos\theta = (\vec{u}\cdot\vec{v})/(\|\vec{u}\|\|\vec{v}\|)$, which we define to be the angle between them. Without Cauchy–Schwarz, this ratio could exceed $1$ and the inverse cosine would be undefined.

## 9.20 Triangle Inequality

Q: Why does the triangle inequality follow from Cauchy–Schwarz?
A: Expand $\|\vec{u}+\vec{v}\|^2 = \|\vec{u}\|^2 + 2\vec{u}\cdot\vec{v} + \|\vec{v}\|^2 \leq \|\vec{u}\|^2 + 2\|\vec{u}\|\|\vec{v}\| + \|\vec{v}\|^2 = (\|\vec{u}\|+\|\vec{v}\|)^2$, using Cauchy–Schwarz on the middle term. Taking square roots gives $\|\vec{u}+\vec{v}\| \leq \|\vec{u}\|+\|\vec{v}\|$. Geometrically: going directly is no longer than going via a third point.

C: [Triangle inequality]: for all $\vec{u}, \vec{v}$ in an inner product space, $\|\vec{u}+\vec{v}\| \leq \|\vec{u}\| + \|\vec{v}\|$.

## 9.21 Worked Example — Projection Onto a Subspace

P: Find the orthogonal projection of $\vec{x}$ onto $W = \text{span}\{\vec{u}_1, \vec{u}_2\}$, given that $\{\vec{u}_1, \vec{u}_2\}$ is an orthogonal set in $\mathbb{R}^n$.

S:
**IDENTIFY**: Projection onto a subspace with a known orthogonal basis. Because the basis is orthogonal, we can apply the sum-of-line-projections formula; no system-solving (and no Gram–Schmidt) is required.

**PLAN**:
- Use $\text{proj}_W\vec{x} = \sum_i \frac{\vec{x}\cdot\vec{u}_i}{\vec{u}_i\cdot\vec{u}_i}\vec{u}_i$.
- Compute each coefficient $c_i = (\vec{x}\cdot\vec{u}_i)/(\vec{u}_i\cdot\vec{u}_i)$ independently, exploiting the orthogonality of the $\vec{u}_i$.
- Assemble the projection as $c_1\vec{u}_1 + c_2\vec{u}_2$.

**EXECUTE**:
1. Verify the basis is orthogonal: confirm $\vec{u}_1\cdot\vec{u}_2 = 0$.
2. Compute $\vec{u}_1\cdot\vec{u}_1$ and $\vec{u}_2\cdot\vec{u}_2$ (these are $\|\vec{u}_1\|^2$ and $\|\vec{u}_2\|^2$).
3. Compute $\vec{x}\cdot\vec{u}_1$ and $\vec{x}\cdot\vec{u}_2$.
4. Form $c_1 = (\vec{x}\cdot\vec{u}_1)/(\vec{u}_1\cdot\vec{u}_1)$ and $c_2 = (\vec{x}\cdot\vec{u}_2)/(\vec{u}_2\cdot\vec{u}_2)$.
5. Output $\text{proj}_W\vec{x} = c_1\vec{u}_1 + c_2\vec{u}_2$.

**EVALUATE**:
- Check the residual: $\vec{z} = \vec{x} - \text{proj}_W\vec{x}$ should satisfy $\vec{z}\cdot\vec{u}_1 = 0$ and $\vec{z}\cdot\vec{u}_2 = 0$ (so $\vec{z} \in W^\perp$).
- If the $\vec{u}_i$ happened to be unit vectors, the formula reduces to $c_i = \vec{x}\cdot\vec{u}_i$, giving a quick sanity check.
- By the best-approximation theorem, this is the unique point of $W$ closest to $\vec{x}$.
