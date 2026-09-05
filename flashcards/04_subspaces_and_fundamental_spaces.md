+++
order = 4
subject = "mathematics"
authoring_model = "gpt-5.6-sol"
authoring_run_id = "local-2026-09-04T19-05-30-913Z-f812cdaa"
authoring_provider = "openai"
authoring_reasoning_effort = "high"
curriculum_model = "gpt-5.6-sol"
curriculum_run_id = "request-25"
curriculum_provider = "openai"
curriculum_reasoning_effort = "high"
tags = ["linear-algebra", "vector-spaces", "subspaces", "rank"]
prerequisites = ["chapter:03_matrices_and_coordinate_transformations"]
provides = [
  "vector-space",
  "subspace",
  "subspace-test",
  "null-space",
  "column-space",
  "row-space",
  "left-null-space",
  "image-of-linear-transformation",
  "kernel-of-linear-transformation",
  "matrix-rank",
  "fundamental-subspaces",
]
+++

# Subspaces and fundamental spaces

## Vector spaces

<!-- card-id: 6a160e94-30fc-4057-bf53-b28abc52e7c0 -->
Q: The notation \(\mathbb R^n\) names the collection of all \(n\)-entry coordinate vectors whose entries are real numbers. What does \(\mathbb R^3\) contain?
A: **It contains every three-entry real coordinate vector.**

<!-- card-id: 7e53526c-f779-4395-849f-bca787f711ea -->
Q: A **real vector space** is a collection \(V\) with rules for adding its objects and multiplying them by real numbers. Its objects are called vectors. Could a matrix be a vector in this sense?
A: **Yes; a matrix can be a vector when it is an object in such a collection \(V\).**

<!-- card-id: 1af15620-0ddb-4748-ad57-fae8d586267d -->
Q: **Additive closure** is one vector-space law. If \(\mathbf u\) and \(\mathbf v\) are vectors in \(V\), where must \(\mathbf u+\mathbf v\) lie?
A: **The sum \(\mathbf u+\mathbf v\) must also lie in \(V\).**

<!-- card-id: cb6b78d3-6bc2-4d6d-a904-b304ca4b0b36 -->
Q: **Scalar closure** is one vector-space law. If \(\mathbf u\) is in \(V\) and \(c\) is any real scalar, where must \(c\mathbf u\) lie?
A: **The scaled vector \(c\mathbf u\) must also lie in \(V\).**

<!-- card-id: 2c9c0a1b-f1d6-4f30-af15-e831411f16ef -->
Q: The commutative law says that changing the order of two vectors in a sum does not change the result. Write this law for vectors \(\mathbf u,\mathbf v\) in \(V\).
A: **The law is \(\mathbf u+\mathbf v=\mathbf v+\mathbf u\).**

<!-- card-id: 88909be1-3477-41db-b49a-32a3b513db5c -->
Q: The associative law says that regrouping three vectors in a sum does not change the result. Write this law for vectors \(\mathbf u,\mathbf v,\mathbf w\) in \(V\).
A: **The law is \((\mathbf u+\mathbf v)+\mathbf w=\mathbf u+(\mathbf v+\mathbf w)\).**

<!-- card-id: d3bf97e1-9b3c-4b8c-b410-239dd70f6942 -->
Q: A vector space has a zero vector \(\mathbf 0\) that acts as the additive identity. What equation states this role for every vector \(\mathbf u\) in \(V\)?
A: **The identity law is \(\mathbf u+\mathbf 0=\mathbf u\).**

<!-- card-id: c66398b3-482c-4f8a-9649-bf720f065664 -->
Q: Every vector \(\mathbf u\) in a vector space has an additive inverse written \(-\mathbf u\). What equation defines that inverse?
A: **The defining equation is \(\mathbf u+(-\mathbf u)=\mathbf 0\).**

<!-- card-id: e3e69540-c0aa-4ecf-ad93-3bb42ec9671b -->
Q: Multiplication by the real scalar \(1\) must leave every vector unchanged. What is the corresponding vector-space law?
A: **The law is \(1\mathbf u=\mathbf u\) for every vector \(\mathbf u\) in \(V\).**

<!-- card-id: bb08101e-395b-4559-88f3-ae02f6eb7ba9 -->
Q: Successive scaling must agree with multiplying the two real scalars first. Write this law for real scalars \(a,b\) and a vector \(\mathbf u\) in \(V\).
A: **The law is \(a(b\mathbf u)=(ab)\mathbf u\).**

<!-- card-id: 85297eb8-8aa1-4bb8-aaa4-e5c542d77434 -->
Q: Scaling must distribute over vector addition. Write this law for a real scalar \(a\) and vectors \(\mathbf u,\mathbf v\) in \(V\).
A: **The law is \(a(\mathbf u+\mathbf v)=a\mathbf u+a\mathbf v\).**

<!-- card-id: 84353f87-7d4f-4501-b969-e225b8e8a692 -->
Q: Adding two real scalars before scaling a vector must agree with adding the two separately scaled vectors. Write this law for real scalars \(a,b\) and a vector \(\mathbf u\) in \(V\).
A: **The law is \((a+b)\mathbf u=a\mathbf u+b\mathbf u\).**

<!-- card-id: d26214af-79bb-4142-bf71-287e8a526316 -->
Q: Why is \(\mathbb R^n\), with entrywise vector addition and scalar multiplication, a real vector space?
A: **Those operations keep \(n\)-entry real vectors inside \(\mathbb R^n\), and every required law holds entry by entry because it holds for real numbers.**

<!-- card-id: 616bc192-7003-49c5-8ed6-35433c75709b -->
Q: Why do all real \(2\times3\) matrices form a real vector space under the established entrywise addition and scaling rules?
A: **Adding or scaling \(2\times3\) matrices preserves the shape, and the required laws hold in every entry.**

## Subspaces

<!-- card-id: 5459dac9-9358-4121-ab52-a084d442abef -->
Q: The notation \(\mathbf u\in V\) means that \(\mathbf u\) is a member of the collection \(V\). What does \(\mathbf w\in W\) say in words?
A: **It says that \(\mathbf w\) belongs to \(W\).**

<!-- card-id: 5e8ed881-98a1-4ac4-9cbc-a25351e952f8 -->
Q: The notation \(W\subseteq V\) means that every member of \(W\) also belongs to \(V\). If \(W\subseteq V\) and \(\mathbf w\in W\), what follows?
A: **It follows that \(\mathbf w\in V\).**

<!-- card-id: 1cb301ab-cabc-45b7-b987-62604044ac5e -->
Q: Suppose \(W\subseteq V\). Saying that \(W\) uses the **inherited operations** means that its addition and scaling are exactly the operations already used in \(V\). If \(\mathbf u,\mathbf v\in W\), which addition rule is used to form \(\mathbf u+\mathbf v\)?
A: **Use the same vector-addition rule that \(V\) uses.**

<!-- card-id: c0c04658-f35f-4568-b52a-cd99e90a3190 -->
Q: A **subspace** of a vector space \(V\) is a subset \(W\subseteq V\) that is itself a vector space under the inherited operations. What relationship does the word “subspace” assert between \(W\) and \(V\)?
A: **It asserts that \(W\) is a vector space contained in \(V\) and uses \(V\)'s operations.**

<!-- card-id: ffa71fff-9dbc-481a-9587-f9a6ddf0b522 -->
Q: What zero-vector condition must a subset \(W\) of a known vector space \(V\) satisfy to be a subspace?
A: **The zero vector of \(V\) must belong to \(W\).**

<!-- card-id: cb103cd6-fabe-4da8-8136-acbec8ee71eb -->
Q: What addition condition must a subset \(W\) of a known vector space satisfy to be a subspace?
A: **Whenever \(\mathbf u,\mathbf v\in W\), their sum \(\mathbf u+\mathbf v\) must also belong to \(W\).**

<!-- card-id: 3daf652f-8af3-4b3f-a265-8ffb0dd95fb5 -->
Q: What scaling condition must a subset \(W\) of a real vector space satisfy to be a subspace?
A: **Whenever \(\mathbf u\in W\) and \(c\) is real, the vector \(c\mathbf u\) must also belong to \(W\).**

<!-- card-id: bdc6976e-47e4-4925-917c-dd1505f8f12b -->
Q: A subset \(W\) of a known vector space contains the zero vector and is closed under addition and real-scalar multiplication. What does the **subspace test** let you conclude?
A: **The subspace test concludes that \(W\) is a subspace.**

<!-- card-id: c9fe5c20-88a6-4a18-9aa1-57591c1766bd -->
P: Let \(W\) be the collection of all vectors \(\left[\begin{array}{r}x\\y\\z\end{array}\right]\in\mathbb R^3\) satisfying \(x+y-z=0\). Use the subspace test to decide whether \(W\) is a subspace of \(\mathbb R^3\).
S: **IDENTIFY**

This is a subspace decision for a subset defined by a homogeneous coordinate equation.

**PLAN**

Check the zero vector, addition closure, and scalar closure using the defining equation.

**EXECUTE**

**The collection \(W\) is a subspace of \(\mathbb R^3\).** The zero vector satisfies the equation; if \(x+y-z=0\) and \(p+q-r=0\), then \((x+p)+(y+q)-(z+r)=0\); and scaling a solution by \(c\) gives \(c(x+y-z)=0\).

**EVALUATE**

All three subspace-test conditions return vectors that still satisfy the same zero-target equation.

<!-- card-id: d76c4306-4bde-4545-b5e4-8a07bf4a17b7 -->
Q: Why is the span of any listed vectors a subspace of the vector space containing those vectors?
A: **A span contains the zero combination, and adding or scaling linear combinations produces another linear combination of the same listed vectors.**

<!-- card-id: 053b7d30-e6d9-4307-9f02-3e5c1e33a70a -->
Q: Why is the one-vector collection \(\{\mathbf 0\}\) a subspace of every vector space \(V\)?
A: **It contains \(\mathbf 0\), and adding or scaling its only vector always returns \(\mathbf 0\).**

<!-- card-id: a5d8d561-a281-405f-9606-1604945e5029 -->
Q: Let \(W\) contain all two-entry real coordinate vectors whose first entry is \(1\). One failed case disproves an always-required condition. Give a vector in \(W\) and a real scalar whose product is not in \(W\).
A: **The vector \(\left[\begin{array}{r}1\\0\end{array}\right]\) lies in \(W\), but twice it is \(\left[\begin{array}{r}2\\0\end{array}\right]\), which does not.**

<!-- card-id: 1ee374d9-0a14-49fd-83c5-9bb5a036f488 -->
Q: Let \(A\mathbf x=\mathbf b\) be consistent with \(\mathbf b\ne\mathbf 0\). Which subspace-test condition does its solution collection fail immediately?
A: **It fails the zero-vector condition because \(A\mathbf 0=\mathbf 0\ne\mathbf b\).**

## Null spaces and kernels

<!-- card-id: eef0e657-488c-4c90-9644-51a75a9bbb52 -->
Q: The **null space** of a matrix \(A\), written \(N(A)\), is the collection of inputs that \(A\) sends to the zero vector. Which equation decides whether \(\mathbf x\in N(A)\)?
A: **The membership equation is \(A\mathbf x=\mathbf 0\).**

<!-- card-id: a2aeebde-9fa8-42cf-8b32-344919104b54 -->
Q: If \(A\) has shape \(m\times n\), why is \(N(A)\) a subset of \(\mathbb R^n\) rather than \(\mathbb R^m\)?
A: **Vectors in \(N(A)\) are inputs to \(A\), so each must have one entry for each of the \(n\) columns.**

<!-- card-id: b18e96d2-ac1e-4ab0-8af1-02a98950741f -->
Q: Why does \(N(A)\) always pass the zero-vector condition of the subspace test?
A: **Because \(A\mathbf 0=\mathbf 0\), the input zero vector belongs to \(N(A)\).**

<!-- card-id: 3f1a92c4-cf81-4946-a3e1-5305640ffa2a -->
Q: If \(\mathbf u,\mathbf v\in N(A)\), why must \(\mathbf u+\mathbf v\in N(A)\)?
A: **Linearity gives \(A(\mathbf u+\mathbf v)=A\mathbf u+A\mathbf v=\mathbf 0+\mathbf 0=\mathbf 0\).**

<!-- card-id: a9739f29-7bf4-4299-ae6a-79a293e00c2d -->
Q: If \(\mathbf u\in N(A)\) and \(c\) is real, why must \(c\mathbf u\in N(A)\)?
A: **Linearity gives \(A(c\mathbf u)=c(A\mathbf u)=c\mathbf 0=\mathbf 0\).**

<!-- card-id: fd38ee1f-9b15-43f4-bf53-e9b700e30113 -->
Q: What follows from the facts that \(N(A)\) contains zero and is closed under addition and real-scalar multiplication?
A: **The subspace test shows that \(N(A)\) is a subspace of the input space.**

<!-- card-id: 748327c8-db25-4c5d-abf8-38e6e1cf790e -->
P: Find \(N(A)\) in span form for \(A=\left[\begin{array}{rrr}1&2&1\\0&1&-1\end{array}\right]\).
S: **IDENTIFY**

This is a null-space calculation, so the target equation is \(A\mathbf x=\mathbf 0\).

**PLAN**

Solve the homogeneous system, choose a parameter for the free variable, and factor the solution vector.

**EXECUTE**

**The null space is \(N(A)=\operatorname{span}\left\{\left[\begin{array}{r}-3\\1\\1\end{array}\right]\right\}\).** The equations give \(x_2=x_3\) and \(x_1=-3x_3\), so with \(x_3=t\), every solution is \(t\left[\begin{array}{r}-3\\1\\1\end{array}\right]\).

**EVALUATE**

Multiplying \(A\left[\begin{array}{r}-3\\1\\1\end{array}\right]\) gives \(\left[\begin{array}{r}0\\0\end{array}\right]\), so every displayed scalar multiple belongs to \(N(A)\).

<!-- card-id: 19210856-f1fc-469b-a1a9-2a399f72035e -->
Q: The **kernel** of a linear transformation \(T\), written \(\ker(T)\), is the collection of allowed inputs that \(T\) sends to the zero output. If \(T(\mathbf u)=\mathbf 0\), where does \(\mathbf u\) belong?
A: **The input \(\mathbf u\) belongs to the kernel of \(T\).**

<!-- card-id: 21d8cc66-6095-4db2-845c-5352286765f1 -->
Q: If a linear coordinate transformation is \(T(\mathbf x)=A\mathbf x\), how are the kernel of \(T\) and the null space of \(A\) related?
A: **They are the same collection of inputs: \(\ker(T)=N(A)\).**

## Column spaces and images

<!-- card-id: 2a9f4a5f-c3d5-4992-9667-02f49230c4b8 -->
Q: The **column space** of \(A\), written \(\operatorname{Col}(A)\), is the span of the columns of \(A\). What form must a vector have to belong to \(\operatorname{Col}(A)\)?
A: **It must be a linear combination of the columns of \(A\).**

<!-- card-id: 76c42353-2942-469e-862c-881a8678a528 -->
Q: If \(A\) has shape \(m\times n\), why is \(\operatorname{Col}(A)\) a subset of \(\mathbb R^m\)?
A: **Each column of \(A\) has \(m\) entries, so every linear combination of the columns is an \(m\)-entry vector.**

<!-- card-id: 2229f08c-c20e-4d30-a5e9-404ca76fb041 -->
Q: The **image** of a transformation \(T\) is the collection of all attainable outputs \(T(\mathbf x)\). If \(\mathbf y=T(\mathbf x)\) for an allowed input \(\mathbf x\), where does \(\mathbf y\) belong?
A: **The output \(\mathbf y\) belongs to the image of \(T\).**

<!-- card-id: fbba2858-d2fa-467f-acc4-1c9c000b64e6 -->
Q: If \(T(\mathbf x)=A\mathbf x\), why is the image of \(T\) equal to \(\operatorname{Col}(A)\)?
A: **Every output \(A\mathbf x\) is a linear combination of the columns of \(A\), and every such column combination is produced by using its coefficients as an input.**

<!-- card-id: 237fbfa4-8a5d-4326-8336-3c1604a45be1 -->
Q: What column-space condition is equivalent to consistency of the matrix equation \(A\mathbf x=\mathbf b\)?
A: **The equation is consistent exactly when \(\mathbf b\in\operatorname{Col}(A)\).**

<!-- card-id: ae540adf-683d-4a03-b8fd-01e677a57a0e -->
P: Let \(A=\left[\begin{array}{rr}1&2\\0&1\end{array}\right]\) and \(\mathbf b=\left[\begin{array}{r}5\\2\end{array}\right]\). Decide whether \(\mathbf b\in\operatorname{Col}(A)\), and give a coefficient certificate.
S: **IDENTIFY**

This is column-space membership, equivalent to solving \(A\mathbf x=\mathbf b\).

**PLAN**

Use the two entries of \(\mathbf x\) as coefficients on the columns and solve the resulting system.

**EXECUTE**

**Yes; \(\mathbf b\in\operatorname{Col}(A)\) because \(\mathbf b=1\left[\begin{array}{r}1\\0\end{array}\right]+2\left[\begin{array}{r}2\\1\end{array}\right]\).** The coefficient system gives \(x_2=2\) and \(x_1=1\).

**EVALUATE**

The certified combination equals \(\left[\begin{array}{r}1+4\\0+2\end{array}\right]=\left[\begin{array}{r}5\\2\end{array}\right]\), matching \(\mathbf b\).

<!-- card-id: f7bc2802-2c72-44b6-8885-69b4e9439367 -->
Q: Why is \(\operatorname{Col}(A)\) always a subspace of \(\mathbb R^m\) for an \(m\times n\) matrix \(A\)?
A: **It is the span of the columns of \(A\), and every span is a subspace.**

## Row spaces

<!-- card-id: c286ac05-2be6-4fba-9bd6-6e9492625e11 -->
Q: The **row space** of \(A\), written \(\operatorname{Row}(A)\), is the span of the rows of \(A\), with each row read as a coordinate vector. What form must a member of \(\operatorname{Row}(A)\) have?
A: **It must be a linear combination of the rows of \(A\).**

<!-- card-id: 15e6daf3-b33c-4a45-b378-d7672dea7b06 -->
Q: Why is \(\operatorname{Row}(A)=\operatorname{Col}(A^{\mathsf T})\)?
A: **The rows of \(A\) become the columns of \(A^{\mathsf T}\), so the two spans use the same vectors.**

<!-- card-id: b71eda23-d16e-45ec-a072-794d5ff35c3a -->
Q: If \(A\) has shape \(m\times n\), why is \(\operatorname{Row}(A)\) a subset of \(\mathbb R^n\)?
A: **Each row of \(A\) has \(n\) entries, so every row combination is an \(n\)-entry vector.**

<!-- card-id: 416605b2-2620-4482-993f-6e91af4ba79d -->
Q: After one elementary row operation changes \(A\) to \(B\), why does every row of \(B\) belong to \(\operatorname{Row}(A)\)?
A: **Each new row is a linear combination of the old rows, so every new row lies in the old row span.**

<!-- card-id: 653d1d9e-7016-488c-963f-ef407a0554b0 -->
Q: Elementary row operations are reversible. How does that fact turn \(\operatorname{Row}(B)\subseteq\operatorname{Row}(A)\) into equality after row reduction?
A: **The reverse row operation also gives \(\operatorname{Row}(A)\subseteq\operatorname{Row}(B)\), so the two row spaces are equal.**

<!-- card-id: 14243d00-e5d7-485d-b049-b3c5f087036d -->
Q: Why can zero rows of an RREF matrix be omitted when listing vectors that span its row space?
A: **Adding the zero vector to a spanning list creates no new linear combinations.**

<!-- card-id: 557cbf6a-43d1-47e0-bec5-5566096d4ff5 -->
P: The matrix \(A\) row-reduces to \(R=\left[\begin{array}{rrr}1&0&1\\0&1&1\\0&0&0\end{array}\right]\). Give a spanning description of \(\operatorname{Row}(A)\).
S: **IDENTIFY**

This is row-space extraction from a row-equivalent RREF matrix.

**PLAN**

Use preservation of row space under row operations, then keep the nonzero rows of \(R\).

**EXECUTE**

**The row space is \(\operatorname{Row}(A)=\operatorname{span}\left\{\left[\begin{array}{r}1\\0\\1\end{array}\right],\left[\begin{array}{r}0\\1\\1\end{array}\right]\right\}\).** The zero row contributes no additional combinations.

**EVALUATE**

Both displayed vectors have three entries, as every row of the original three-column matrix must.

## Left null spaces and the four-space map

<!-- card-id: 7dfedc32-5c99-4877-8bb7-912fad921262 -->
Q: The **left null space** of \(A\) is defined as the null space of its transpose, \(N(A^{\mathsf T})\). Which equation decides whether \(\mathbf y\) belongs to the left null space?
A: **The membership equation is \(A^{\mathsf T}\mathbf y=\mathbf 0\).**

<!-- card-id: d624d7ad-67da-43cb-934b-574fba18a96f -->
Q: If \(A\) has shape \(m\times n\), why is its left null space a subset of \(\mathbb R^m\)?
A: **The transpose \(A^{\mathsf T}\) has \(m\) columns, so its allowed input \(\mathbf y\) has \(m\) entries.**

<!-- card-id: b1d130a2-642f-4ac9-a172-d8da0ac25d4c -->
P: Find the left null space of \(A=\left[\begin{array}{rr}1&0\\0&1\\1&1\end{array}\right]\) in span form.
S: **IDENTIFY**

This is a left-null-space calculation, so solve \(A^{\mathsf T}\mathbf y=\mathbf 0\).

**PLAN**

Transpose \(A\), solve the resulting homogeneous system, and factor the parameter from \(\mathbf y\).

**EXECUTE**

**The left null space is \(N(A^{\mathsf T})=\operatorname{span}\left\{\left[\begin{array}{r}-1\\-1\\1\end{array}\right]\right\}\).** The equations are \(y_1+y_3=0\) and \(y_2+y_3=0\), so \(\mathbf y=t\left[\begin{array}{r}-1\\-1\\1\end{array}\right]\).

**EVALUATE**

Multiplication gives \(A^{\mathsf T}\left[\begin{array}{r}-1\\-1\\1\end{array}\right]=\left[\begin{array}{r}0\\0\end{array}\right]\), confirming the generator.

<!-- card-id: e7576ebb-5f18-4b4a-8419-2ea007b1aa6d -->
Q: For an \(m\times n\) matrix, the diagram's solid arrow sends \(n\)-entry inputs through \(A\), and the dashed arrow sends \(m\)-entry inputs through \(A^{\mathsf T}\). Which null-related space lives in the left panel?

![Two coordinate-vector panels, with A pointing from the n-entry input side to the m-entry output side and A transpose pointing back.](../figures/04_subspaces_and_fundamental_spaces/fundamental_space_sides.svg)
A: **The left panel contains \(N(A)\), because its vectors are \(n\)-entry inputs to \(A\).**

<!-- card-id: 7ff68399-5d3f-48ed-86f6-17979af4b9d8 -->
Q: For an \(m\times n\) matrix, the diagram's left panel contains \(n\)-entry coordinate vectors. Which span-related space belongs in that panel?

![Two coordinate-vector panels, with A pointing from the n-entry input side to the m-entry output side and A transpose pointing back.](../figures/04_subspaces_and_fundamental_spaces/fundamental_space_sides.svg)
A: **The left panel contains \(\operatorname{Row}(A)\), because every row has \(n\) entries.**

<!-- card-id: ca03e33c-2074-4a1a-aa40-64ce9da1262c -->
Q: For an \(m\times n\) matrix, the diagram's right panel contains \(m\)-entry coordinate vectors. Which span-related space belongs in that panel?

![Two coordinate-vector panels, with A pointing from the n-entry input side to the m-entry output side and A transpose pointing back.](../figures/04_subspaces_and_fundamental_spaces/fundamental_space_sides.svg)
A: **The right panel contains \(\operatorname{Col}(A)\), because every column has \(m\) entries.**

<!-- card-id: 32fae25a-af2a-4322-a081-ec8c1ff2d207 -->
Q: For an \(m\times n\) matrix, the diagram's dashed arrow treats \(m\)-entry vectors as inputs to \(A^{\mathsf T}\). Which null-related space therefore lives in the right panel?

![Two coordinate-vector panels, with A pointing from the n-entry input side to the m-entry output side and A transpose pointing back.](../figures/04_subspaces_and_fundamental_spaces/fundamental_space_sides.svg)
A: **The right panel contains \(N(A^{\mathsf T})\), the left null space of \(A\).**

## Rank and fundamental-space synthesis

<!-- card-id: ae4de958-99e3-4aa6-9036-00095ed9d9d9 -->
Q: An echelon form of \(A\) has \(r\) pivot positions. The **rank** of \(A\) is defined from this feature. What is \(\operatorname{rank}(A)\)?
A: **The rank is \(r\), the number of pivot positions.**

<!-- card-id: ab7852fa-93f5-47a9-9d43-e13f036a9fee -->
Q: An echelon form of \(A\) is \(\left[\begin{array}{rrrr}1&2&0&3\\0&0&1&-1\\0&0&0&0\end{array}\right]\). What is \(\operatorname{rank}(A)\)?
A: **The rank is \(2\), because the echelon matrix has two pivot positions.**

<!-- card-id: 8cf924b9-7e5e-4e85-8ca5-5090e169b6df -->
Q: Row reduction shows that the pivot positions of \(A\) occur in columns 1 and 3. To span \(\operatorname{Col}(A)\), should you take columns 1 and 3 from \(A\) or from its RREF?
A: **Take columns 1 and 3 from the original matrix \(A\); row reduction generally changes the column space.**

<!-- card-id: 12af5425-51c3-4093-98a1-67c0fac83777 -->
Q: How can the nonzero rows of an RREF matrix be used to read the rank of the original matrix?
A: **The number of nonzero RREF rows equals the rank.**

<!-- card-id: fd864615-6c1d-483e-bffe-ce02f11b8bad -->
Q: Compare \(\operatorname{rank}(A)\) with the number of nonzero RREF rows and the number of original columns selected by pivot positions.
A: **The rank equals both the number of nonzero RREF rows and the number of original columns selected by pivot positions.**

<!-- card-id: 0133ece1-70bf-464f-a24f-aa650c98ed69 -->
P: The matrix
\[
A=\left[\begin{array}{rrr}1&2&3\\2&4&6\\0&1&1\end{array}\right]
\]
has RREF
\[
R=\left[\begin{array}{rrr}1&0&1\\0&1&1\\0&0&0\end{array}\right].
\]
Give a spanning description of \(\operatorname{Col}(A)\).
S: **IDENTIFY**

This is column-space extraction using pivot positions from a row-reduction record.

**PLAN**

Locate the pivot columns in \(R\), then take the columns in those positions from the original matrix \(A\).

**EXECUTE**

**The column space is \(\operatorname{Col}(A)=\operatorname{span}\left\{\left[\begin{array}{r}1\\2\\0\end{array}\right],\left[\begin{array}{r}2\\4\\1\end{array}\right]\right\}\).** The pivots of \(R\) occur in columns 1 and 2, so those positions select the first two columns of \(A\).

**EVALUATE**

The unselected third column is the sum of the two selected columns, so it already lies in the displayed span.

<!-- card-id: a1668050-7b62-45ec-a0c8-4e049775e987 -->
Q: What collective name is given to the four matrix spaces \(N(A)\), \(\operatorname{Col}(A)\), \(\operatorname{Row}(A)\), and \(N(A^{\mathsf T})\)?
A: **They are the four fundamental spaces of \(A\).**

<!-- card-id: 336ba51b-af9d-48dd-ab5f-2fa5d53e0f80 -->
Q: For \(T(\mathbf x)=A\mathbf x\), which established space answers “which inputs are sent to zero?” and which answers “which outputs are attainable?”
A: **The kernel \(N(A)\) answers the input-to-zero question, while the image \(\operatorname{Col}(A)\) answers the attainable-output question.**
