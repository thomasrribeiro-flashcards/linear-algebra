# Linear Algebra

Reason with vector spaces, linear maps, matrices, rank, determinants,
eigenstructure, inner products, orthogonality, and matrix factorizations across
algebraic, geometric, and computational views.

## Scope

- Subject: `mathematics`
- Learner level: `undergraduate-core`
- Confirmed mathematical prerequisites: the **scheduled** portion of
  `mathematics/elementary-algebra-and-functions` currently establishes
  variables, algebraic expressions, equations as equality statements,
  substitution and evaluation, verbal-expression translation, equivalent
  expressions, operation properties, distribution, like terms, and expression
  simplification, equation solutions, equality properties, one-step equations,
  and equation checking. Planned but unscheduled prerequisite chapters are not
  treated as mastered.
- Confirmed tools: none. All required reasoning and representative small
  computations remain possible by hand; optional software-based exploration
  belongs in external practice.
- Machine-readable deck and tool prerequisites: `deck.toml`.
- What mastery enables: formulate and solve finite linear systems; translate
  among equations, vectors, matrices, transformations, and geometric views;
  reason with finite-dimensional vector spaces, bases, dimension, rank, and
  nullity; use determinants, eigenstructure, inner products, orthogonality,
  least squares, duality, elementary tensors, and the principal matrix
  factorizations; and enter downstream work in differential equations,
  multivariable calculus, abstract algebra, numerical analysis, optimization,
  stochastic processes, geometry, graphics, and data-oriented subjects.
- Scalar convention: begin over the real numbers and introduce complex scalars
  before the finite-dimensional spectral theorem and singular value
  decomposition. Vectors are columns unless a different orientation is stated.
- Deliberate exclusions: calculus-dependent models, differential equations,
  probability and Markov chains, computer-graphics pipelines, data-science
  methods, floating-point stability, large-scale numerical algorithms,
  iterative solvers, Jordan canonical form, and proof techniques not developed
  locally. Those belong to the named downstream decks or to a later course.

Chapter 1 contains the 27-card cold-start pilot for systems and elimination.
Chapter 2 contains 23 cards on coordinate vectors, vector operations, linear
combinations, vector equations, span, and homogeneous systems, with two
retrieval figures. Chapter 3 contains 26 cards on matrices, matrix operations,
coordinate transformations, and composition, with two retrieval figures.
Chapter 4 contains 30 cards on vector spaces, the subspace test, kernels,
images, the four fundamental spaces, and rank, with one relational retrieval
figure. Chapters 5–11 remain curriculum-only and have not been authored.
Representation decisions and intentional omissions are recorded in
`CARD_README.md` and the chapter cold-start audits.

## Chapter map

| File | Topic | Learning outcomes |
|---|---|---|
| `01_linear_systems_and_elimination.md` | Linear systems and elimination | Translate small simultaneous linear equations into augmented matrices; preserve solution sets under row operations; classify and parametrize the solution set from echelon and reduced echelon forms. |
| `02_vectors_linear_combinations_and_span.md` | Vectors, linear combinations, and span | Operate on coordinate vectors, interpret vector equations, and decide whether a vector lies in the span of a set using the system viewpoint. |
| `03_matrices_and_coordinate_transformations.md` | Matrices and coordinate transformations | Compute with matrices, interpret matrix-vector multiplication as a coordinate transformation, and connect matrix multiplication with composition. |
| `04_subspaces_and_fundamental_spaces.md` | Subspaces and fundamental spaces | Test subspace conditions and relate column, row, null, and left-null spaces to homogeneous and nonhomogeneous systems and rank. |
| `05_independence_basis_and_dimension.md` | Independence, basis, and dimension | Diagnose dependence, construct bases, assign coordinates relative to a basis, and use dimension and rank-nullity. |
| `06_invertibility_factorization_and_change_of_basis.md` | Invertibility, factorization, and change of basis | Connect inverse maps, pivots, kernels, and solvability; use elementary matrices and LU factorization; translate coordinates between bases. |
| `07_determinants_and_volume.md` | Determinants and volume | Compute and reason with determinants as orientation-sensitive scale factors, connect their properties to row operations and products, and use the determinant invertibility test. |
| `08_eigenvalues_invariant_subspaces_and_diagonalization.md` | Eigenvalues, invariant subspaces, and diagonalization | Find and interpret eigendata, identify invariant directions and subspaces, decide diagonalizability, and use similarity and diagonal form. |
| `09_inner_products_orthogonality_and_least_squares.md` | Inner products, orthogonality, and least squares | Use norms, orthogonality, projections, orthonormal bases, Gram-Schmidt, QR factorization, and least-squares residual geometry. |
| `10_duality_bilinear_forms_and_tensors.md` | Duality, bilinear forms, and tensors | Work with linear functionals, dual bases, bilinear and quadratic forms, multilinear maps, elementary tensor products, and basis-dependent representations. |
| `11_spectral_structure_and_singular_value_decomposition.md` | Spectral structure and singular value decomposition | Use the spectral theorem for real symmetric and complex Hermitian operators, recognize positive definiteness, compute and interpret the SVD and pseudoinverse, and compare LU, QR, eigen-, and singular-value factorizations by purpose. |

Chapter prerequisite edges and provided concepts live only in chapter
frontmatter. Inspect the generated human-readable graph with
`flashcards deck prerequisites .`; do not maintain a second prose graph here.

## Boundary and sequencing decisions

- Calculus and proof decks remain recommended sequencing, not hard
  prerequisites. The first chapters therefore establish systems, coordinate
  vectors, geometric conventions, functions-as-transformations, and the local
  argument patterns they require.
- Matrix computation and geometry motivate abstraction before arbitrary vector
  spaces. Definitions, examples, counterexamples, and short justification
  targets are planned together so the course does not split into disconnected
  computational and theoretical halves.
- Determinants remain in the first course because the deck contract names them
  and they connect invertibility, orientation, volume, and characteristic
  polynomials. They are not used as the primary method for solving systems.
- Tensor coverage is intentionally elementary: duality, bilinear forms,
  multilinearity, tensor products, coordinates, and determinant-as-alternating
  structure. Tensor calculus, exterior algebra beyond the determinant bridge,
  and representation-theoretic tensor methods are handed off to later decks.
- SVD and low-rank structure are included to complete the promised matrix
  factorization capability and to support downstream numerical, graphical, and
  data-facing work. Floating-point analysis and production algorithms remain
  outside this deck.

## Source register

Sources below set curricular scope and sequencing; no source prose, exercises,
or figures are copied. Mathematical claims must be checked again during card
authoring.

| Source | Authority/use | License or terms | Accessed |
|---|---|---|---|
| [MAA, *2015 CUPM Curriculum Guide to Majors in the Mathematical Sciences*, Linear Algebra report](https://maa.org/wp-content/uploads/2024/06/2015-CUPM-Curriculum-Guide.pdf) | Mathematical Association of America curriculum committee; primary scope check for systems, matrices, vector spaces, transformations, determinants, eigenstructure, inner products, proof, applications, and complementary algebraic/geometric/numerical views. | MAA copyright; publicly accessible and consulted for synthesis only. | 2026-08-30 |
| [MIT OpenCourseWare, 18.06SC Linear Algebra syllabus](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/syllabus/) | Undergraduate independent-study course; cross-check for the systems/fundamental-spaces, least-squares/determinants/eigenvalues, and positive-definite/SVD progression, and for the explicit observation that calculus is not required to learn the subject. | CC BY-NC-SA 4.0 unless otherwise noted; used for curricular comparison only. | 2026-08-30 |
| [Rob Beezer, *A First Course in Linear Algebra*, online contents](https://linear.ups.edu/linear.ups.edu/html/section-RREF.html) | Open first-course text designed for ordinary-algebra entry; cross-check for a developmental path from systems and vectors through vector spaces, transformations, change of basis, determinants, and eigenstructure. | GNU Free Documentation License; consulted without reproducing text or exercises. | 2026-08-30 |
| [Jim Hefferon, *Linear Algebra*](https://hefferon.net/linearalgebra/) and [license page](https://hefferon.net/source.html) | Open undergraduate text; cross-check for a motivated computational-to-abstract progression and extensive problem practice suitable for independent study. | Choice of GNU FDL or CC BY-SA 3.0 US; consulted without reproducing text or exercises. | 2026-08-30 |
| [OpenStax, *Precalculus 2e*, §9.6 “Solving Systems with Gaussian Elimination”](https://openstax.org/books/precalculus-2e/pages/9-6-solving-systems-with-gaussian-elimination) | Rice University nonprofit open-textbook program; claim-verification cross-check for augmented matrices, the three reversible row-operation types, echelon form, and the Gaussian-elimination workflow. | CC BY 4.0; consulted for verification only, with original card prose and examples. | 2026-08-30 |
| [David Austin, *Understanding Linear Algebra*, §2.3 “The span of a set of vectors”](https://understandinglinearalgebra.org/sec-span.html) | AIM-approved first-course text; claim-verification cross-check for span as all linear combinations and for testing span membership by consistency of the corresponding coefficient system. | CC BY, as recorded by the AIM Open Textbook Initiative; consulted without copying prose, exercises, or figures. | 2026-08-31 |
| Rob Beezer, *A First Course in Linear Algebra*: [Chapter V, “Vectors”](https://linear.ups.edu/linear.ups.edu/download/fcla-twoA4-2.11.pdf) and [“Homogeneous Systems of Equations”](https://linear.ups.edu/linear.ups.edu/fcla/section-HSE.html) | Open first-course text; claim-verification cross-check for entrywise vector operations, linear combinations, span, and the zero solution of every homogeneous linear system. | GNU Free Documentation License; consulted without copying prose, exercises, or figures. | 2026-08-31 |
| David Austin, *Understanding Linear Algebra*: [§2.2 “Matrix multiplication and linear combinations”](https://understandinglinearalgebra.org/sec-matrices-lin-combs.html), [§2.5 “Matrix transformations”](https://understandinglinearalgebra.org/sec-linear-trans.html), and [colophon](https://understandinglinearalgebra.org/frontmatter-4.html) | Current open first-course text by a university mathematics professor; claim-verification cross-check for matrix shape and entrywise operations, matrix–vector and matrix–matrix products, coordinate transformations, linearity, and composition order. | CC BY 4.0; consulted without copying prose, exercises, or figures. | 2026-08-31 |
| [OpenStax, *Algebra and Trigonometry*, §11.5 “Matrices and Matrix Operations”](https://openstax.org/books/algebra-and-trigonometry/pages/11-5-matrices-and-matrix-operations) | Rice University nonprofit open-textbook program; independent claim-verification cross-check for matrix entries and dimensions, same-shape addition, scalar multiplication, and inner-dimension compatibility for products. | CC BY 4.0; consulted for verification only, with original card prose and examples. | 2026-08-31 |
| David Austin, *Understanding Linear Algebra*, [§3.5 “Subspaces”](https://understandinglinearalgebra.org/sec-subspaces.html) and [colophon](https://understandinglinearalgebra.org/frontmatter-4.html) | Current open first-course text; claim-verification cross-check for subspaces, column and null spaces, solvability as column-space membership, and rank. | CC BY 4.0; consulted without copying prose, exercises, or figures. | 2026-09-03 |
| Rob Beezer, *A First Course in Linear Algebra*, [“Subspaces”](https://linear.ups.edu/linear.ups.edu/html/section-S.html) and [“Four Subsets”](https://linear.ups.edu/linear.ups.edu/html/section-FS.html) | Open first-course text; independent verification of the subspace test and of the null, column, row, and left-null spaces as subspaces. | GNU Free Documentation License; consulted without copying prose, exercises, or figures. | 2026-09-03 |
| [MIT OpenCourseWare, 18.06SC, “The Four Fundamental Subspaces”](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/ax-b-and-the-four-subspaces/the-four-fundamental-subspaces/) | Undergraduate university course materials; claim-verification cross-check for the four spaces, their ambient coordinate lengths, and their connection to rank and solvability. | CC BY-NC-SA 4.0 unless otherwise noted; consulted for verification only. | 2026-09-03 |

### Uncertainty and conditions of use

The MAA report notes legitimate first-course variation, including disagreement
about whether determinants and Gram-Schmidt are core. This deck retains both
because they are part of the local contract and support named downstream
capabilities. MAA and MIT also recommend computational technology, but the
learner contract confirms no tool; software experiments are therefore optional
external practice rather than chapter prerequisites. Deep numerical stability
claims, advanced canonical forms, and application-specific models are deferred
instead of being simplified without their prerequisites.

## Studying

Use this repository with the
[flashcards application](https://github.com/thomasrribeiro/flashcards). Card
review history is keyed by repository-scoped stable IDs, allowing corrective or
presentational improvements without discarding learned schedules. Pair future
cards with untimed written problems, full derivations and proofs, geometric
sketching, and optional computational experiments; SRS will not replace those
activities.
