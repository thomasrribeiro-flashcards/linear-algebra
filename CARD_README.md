# Linear Algebra card blueprint

This file records retrieval decisions specific to this deck. Chapters 1–3
include authored cold-start builds and reconciled inventories; later chapters
remain plans only.

## Learner model

- Level: undergraduate-core, for a motivated adult self-learner working with
  spaced retrieval plus written practice.
- Confirmed mathematical prerequisites: scheduled cards in
  `mathematics/elementary-algebra-and-functions` establish variables,
  expressions, equality statements, substitution, evaluation, verbal
  translation, equivalence, operation properties, distribution, like terms,
  simplification, equation solutions, equality properties, one-step equations,
  and equation checking. Its systems, functions, coordinate-plane, line,
  polynomial, and later chapters currently contain no scheduled cards and are
  not inbound knowledge.
- Confirmed tools: none.
- Capabilities this deck should produce: solve and interpret finite linear
  systems; translate among symbolic, tabular, matrix, transformation, and
  geometric representations; reason with vector spaces and linear maps; use
  bases, dimension, rank-nullity, determinants, eigenstructure, inner products,
  least squares, duality, elementary tensors, spectral structure, and the main
  first-course matrix factorizations; and explain why a method applies and how
  to check its result.
- Important exclusions: calculus-dependent applications, probability models,
  production graphics, statistical learning, numerical conditioning and
  stability, iterative large-scale algorithms, Jordan form, and advanced
  tensor, exterior, and representation theory. These are handoffs, not implied
  prerequisites.
- Conventions: real scalars first; complex scalars introduced before the final
  spectral results; column vectors by default; matrix products act right to
  left as composed transformations. Complex inner products use the convention
  linear in the first argument and conjugate-linear in the second, stated again
  on any card where the choice affects grading.

Unconfirmed subject knowledge is not mastered. A target level describes the
destination, not permission to assume its vocabulary.

## Curriculum and prerequisite graph

The graph begins with simultaneous equations because the confirmed inbound deck
supplies expression manipulation but not systems. Coordinate vectors and the
coordinate-plane grammar are established next, before they appear in matrix or
geometric prompts. Concrete matrices and transformations then motivate
subspaces, independence, basis, dimension, and rank. Invertibility and change
of basis precede determinants; determinants precede characteristic polynomials;
inner products branch from the basis chapter; duality and tensors combine the
basis, determinant, and inner-product threads; the final spectral/SVD synthesis
depends on eigenstructure, orthogonality, and bilinear/quadratic structure.

Only hard knowledge edges appear in chapter frontmatter. File order remains a
presentation order, not an implicit prerequisite. The proof and calculus decks
remain recommended rather than required, so each proof pattern, geometric
grammar, and function-as-transformation idea needed here must be established
locally.

## Concept-dependency ledger

This chapter-level ledger fixes the intended frontier. During pilot authoring,
expand chapter 1 to one row per technical term, symbol, convention, figure
grammar, and procedure, with exact card IDs and front order.

| Chapter frontier | Confirmed inbound or new concept groups | First explanation or analyzed-example plan | First supported retrieval plan | Later application | Status |
|---|---|---|---|---|---|
| 01 Systems | Inbound: equations, equality, substitution, equivalent rewrites. New: simultaneous linear equation, solution tuple, augmented matrix, row operation, echelon/RREF, pivot/free variable, consistency, parametric description. | Bridge one equation to two simultaneous equality constraints, then show each row operation as an equivalent-system rewrite using inbound operation properties. | Identify a valid equivalence-preserving row operation and read one solved/echelon system before independent elimination. | Every later matrix, null-space, inverse, rank, and eigen computation. | planned |
| 02 Vectors | Inbound: chapter 1 system solutions. New: coordinate axis/plane grammar, coordinate vector, vector addition, scalar multiplication, zero vector, linear combination, vector equation, span. | Establish an ordered list both as coordinates and as an arrow/displacement; connect coefficients in a vector equation to chapter 1 unknowns. | Translate among list, arrow, and vector equation, then decide span membership through a supported system setup. | Matrix columns, column space, dependence, bases, eigenspaces, orthogonality. | planned |
| 03 Matrices and maps | Inbound: chapters 1–2. New: matrix entries/shape, matrix-vector product, matrix addition/scaling, identity, transpose, matrix product, coordinate transformation, composition. | Present a matrix first as a compact rule that forms output coordinates from linear combinations of input coordinates. | Predict and compute a transformation output, then discriminate entrywise operations from composition/product. | Fundamental spaces, invertibility, determinants, eigendata, factorizations. | planned |
| 04 Subspaces | Inbound: matrix and vector operations. New: vector space axioms in finite examples, subspace, kernel/null space, image/column space, row space, left null space, rank. | Begin with closure tests on familiar coordinate-vector sets; derive the null and column spaces from systems and matrix maps. | Classify examples/nonexamples and connect solvability of `Ax = b` to membership of `b` in the column space. | Basis, dimension, rank-nullity, invertibility, invariant subspaces. | planned |
| 05 Basis and dimension | Inbound: span and subspaces. New: dependence/independence, generating set, basis, coordinates relative to a basis, dimension, rank-nullity. | Contrast redundant and nonredundant spanning sets before defining independence; build bases by removing or extending vectors. | Diagnose a dependence relation and select/construct a basis with a supported pivot link. | Change of basis, diagonalization, orthonormal bases, dual bases, tensor coordinates. | planned |
| 06 Invertibility and coordinates | Inbound: systems, maps, bases, rank-nullity. New: inverse matrix/map, elementary matrix, invertible-matrix equivalences, triangular factor, LU, coordinate isomorphism, change-of-basis matrix. | Link undoing a coordinate transformation to unique solvability and a trivial kernel; retain elimination steps as elementary matrices. | Choose the decisive invertibility criterion and translate one vector between two established bases. | Determinant criterion, similarity, factorization comparison, dual transformation laws. | planned |
| 07 Determinants | Inbound: square matrices, row operations, invertibility, basis changes. New: determinant, alternating/multilinear behavior in columns, cofactor expansion, signed area/volume scale, orientation. | Motivate determinant by how a square map scales oriented area/volume, then connect row operations to computation. | Predict sign/zero/scale from a transformation or row operation before performing a small computation. | Characteristic polynomial, alternating forms, positive-definite and spectral structure. | planned |
| 08 Eigenstructure | Inbound: determinant, basis, change of basis. New: a local polynomial-factor/root bridge, eigenvalue/vector, eigenspace, characteristic polynomial, algebraic/geometric multiplicity, invariant subspace, similarity, diagonalization. | Establish the small polynomial operations actually needed, then start with directions preserved by a plane transformation and translate `Av = lambda v` to a homogeneous system. | Verify or find eigendata in a supported example, then decide diagonalizability from basis/multiplicity evidence. | Spectral theorem, matrix powers, SVD comparison, downstream differential systems. | planned |
| 09 Orthogonality | Inbound: vectors, bases, matrices. New: dot/inner product, norm, distance, angle, orthogonal complement, projection, residual, least squares, orthonormal basis, Gram-Schmidt, QR. | Establish inner product as a scalar comparison that supports length and perpendicularity; derive projection and residual geometry before normal equations. | Interpret a projection diagram and select exact-solution versus least-squares methods, then execute Gram-Schmidt/QR on small data. | Duality via inner products, quadratic forms, spectral theorem, SVD, pseudoinverse. | planned |
| 10 Duality and tensors | Inbound: bases, change of basis, determinant, inner products. New: linear functional, dual space/basis, bilinear and quadratic form, multilinear map, tensor product, tensor, alternating form. | Introduce a functional as a linear scalar-valued measurement; generalize one input to two and then many before presenting tensor products as the structure representing multilinear behavior. | Evaluate and transform a functional/form in coordinates, then distinguish vectors, covectors, bilinear forms, and tensors by input/output behavior. | Hermitian forms, positive definiteness, determinant reinterpretation, later geometry and representation theory. | planned |
| 11 Spectral/SVD synthesis | Inbound: eigenstructure, orthogonality, quadratic forms. New: symmetric/Hermitian and positive-definite operators, spectral theorem, singular value/vector, SVD, pseudoinverse, matrix 2-norm, low-rank approximation. | Contrast arbitrary diagonalization with orthogonal/unitary diagonalization, then derive singular directions from the positive-semidefinite operator `A* A`. | Match a matrix structure to spectral or singular-value tools and interpret factors geometrically before small computations and mixed factorization choice. | Numerical analysis, optimization, graphics, statistics, functional analysis, random matrices. | planned |

Rejected early examples: line equations, three-dimensional planes, derivatives,
Markov chains, differential systems, rotations described with trigonometric
formulas, regression data, graphics pipelines, and network incidence models.
They depend on unconfirmed or downstream concepts and may appear only after a
minimal local bridge or in the owning later deck.

## Retrieval portfolio and interference map

Future cards should schedule distinct decisions for operational definitions,
translation among representations, qualitative prediction, method selection,
error diagnosis, theorem hypotheses, proof spines, boundary cases, and short
applications. Exact compact clozes are optional and appear only after meaning
has been established. Full multi-step proofs, large eliminations, and software
work remain outside SRS.

| Confusable pair or cluster | Decisive contrast to retrieve |
|---|---|
| equation / expression / system | Equality statement versus quantity name versus several simultaneous constraints. |
| vector / point / coordinate list | Algebraic object versus geometric role versus representation in a chosen basis. |
| scalar multiplication / matrix multiplication | Scaling one object versus composing linear actions. |
| span / subspace / basis | All linear combinations of generators versus a closed set versus an independent spanning coordinate system. |
| kernel / image; row / column space | Inputs sent to zero versus attainable outputs; spaces living in the input versus output coordinate domain. |
| free variable / pivot variable; pivot count / matrix size | A parameter chosen freely versus a variable determined by a pivot equation; rank counts independent directions rather than rows or columns automatically. |
| independence / orthogonality | No nontrivial zero combination versus zero inner products; orthogonality implies independence only for nonzero vectors. |
| inverse / transpose / adjoint | Undoing a bijective map versus swapping indices versus the inner-product-defined partner. |
| equivalence / similarity / row equivalence | Same object/value, same operator in different bases, or same system solution set after row operations. |
| determinant / rank / eigenvalue | Oriented scale factor, dimension of image, or preserved-direction scale. |
| eigendecomposition / SVD | Requires an eigenbasis of a square operator versus always available orthonormal domain/codomain singular directions. |
| bilinear form / inner product / tensor | Two-input linear rule; a positive-definite symmetric/Hermitian special case; a basis-independent multilinear structure or its coordinate array. |
| exact solve / least squares / pseudoinverse | Satisfy all equations, minimize residual norm, or choose the canonical minimum-norm least-squares solution. |

## Chapter design ledger

For chapter 1, the table records the original plan that the pilot ledger below
expands and reconciles. “Include later” remains a plan for unauthored chapters.
Every structured problem retains all IPEE headings. Progressions are targets,
not quotas, and may be shortened when a decision is already secure.

| Chapter | Retrieval targets and basic-card roles | Cloze candidates | Problem/application progression | Authentic representations and figure opportunities |
|---|---|---|---|---|
| 01 Systems | Definitions, solution-set invariance, row-operation choice, consistency classification, pivot/free-variable errors, symbolic↔augmented translation. | Possible after meaning: names of the three row operations and RREF pivot conditions; omit formula-like clozes. | Analyzed equivalence rewrite → completion elimination step → faded RREF reading → independent small solve/parametrization → mixed unique/none/infinite classification. | Equations, tables, augmented matrices, elimination-state sequences. **Include later:** solution-set intersection sketches only after axes/lines are self-bridged; row-operation before/after states. **Omit:** determinant/Cramer visuals because determinant is future. |
| 02 Vectors | Coordinate-vector meaning, operations, linear combinations, span membership, verbal/symbolic/geometric translation, point-vector misconception. | Possible: compact notation for span or the zero vector only after understanding; no cloze required. | Analyzed arrow/list translation → completion linear combination → faded span setup → independent span decision → mixed vector equation/system choice. | Lists, columns, arrows, coordinate grids, vector equations. **Include later:** addition parallelogram, scalar-multiple direction/length, span of one/two vectors. **Omit:** cross product and trigonometric angle diagrams, owned elsewhere. |
| 03 Matrices | Shape/entry meaning, matrix-vector product, identity/transpose, product-as-composition, transformation prediction, dimension-mismatch diagnosis. | Possible: `I` and transpose notation after establishment; multiplication rules are reasoning targets, not clozes. | Analyzed transformation output → completion product entry → faded composition → independent matrix construction from images of basis vectors → mixed operation selection. | Arrays, input/output tables, coordinate grids, transformation pipelines. **Include later:** grid before/after maps, basis-vector image construction, composition order diagram. **Omit:** graphics pipeline scenes and affine homogeneous coordinates. |
| 04 Subspaces | Closure tests, kernel/image meaning, fundamental-space membership, solvability, rank, zero/nonzero affine solution-set contrast. | Possible: null/column-space notation after meaning; avoid four-space list memorization without relational cues. | Analyzed closure test → completion kernel/column calculation → faded membership/consistency → independent fundamental-space relation → mixed subspace/non-subspace diagnosis. | Set-builder, parametric, spanning, equation, and matrix descriptions. **Include later:** subspace-in-ambient-space sketches and domain→kernel/image relational diagram. **Omit:** Venn diagrams that imply false finite-area or disjoint geometry. |
| 05 Basis | Dependence witnesses, basis tests/construction, coordinates, dimension, rank-nullity, redundant-generator diagnosis. | Possible: rank-nullity identity as a complete math-span deletion after conceptual cards; no long definition clozes. | Analyzed redundancy → completion basis extraction → faded coordinate solve → independent basis extension → mixed span/independence/basis decision. | Pivot tables, coordinate columns, geometric spanning sets, abstract examples. **Include later:** dependence collapse, alternative bases on one plane, basis-coordinate translation. **Omit:** decorative basis arrows lacking a comparison task. |
| 06 Invertibility | Equivalent criteria, inverse as undoing, elementary matrices, LU structure, basis-coordinate maps, change-of-basis direction errors. | Possible: compact triangular-factor notation; do not cloze the entire invertible-matrix theorem list. | Analyzed inverse criterion → completion elementary-matrix step → faded LU solve → independent change of basis → mixed inverse/LU/elimination method choice. | Elimination records, factor products, commutative-style coordinate diagrams. **Include later:** forward/inverse transformation pair, LU elimination stages, two-basis coordinate map. **Omit:** floating-point pivoting and conditioning plots. |
| 07 Determinants | Scale/orientation meaning, row-operation effects, multiplicativity, cofactor choice, singularity, formula/geometry discrimination. | Possible: short row-operation effects after conceptual establishment; avoid memorizing expanded formulas by cloze. | Analyzed area scale → completion row-operation update → faded determinant computation → independent invertibility/orientation inference → mixed determinant versus elimination decision. | Symbolic determinant, parallelogram/parallelepiped, transformed grid. **Include later:** area/volume scale, orientation reversal, collapse to lower dimension. **Omit:** Cramer's rule as a main solver; it may appear only as a bounded theorem consequence. |
| 08 Eigenstructure | Eigendata meaning/checks, characteristic equation, eigenspaces, invariant subspaces, field-dependent multiplicities/diagonalizability, similarity, powers. Real eigenstructure comes first; matrices without real eigenvalues are explicit boundary cases until chapter 11 introduces complex scalars. | Possible: `Av = lambda v` only after interpretation; multiplicity terms may use bounded clozes after contrasts. | Analyzed invariant direction → completion eigenvector check → faded eigenspace → independent diagonalization/power → mixed diagonalizable/non-diagonalizable diagnosis. | Transformation arrows, invariant lines/planes, basis-factor diagrams, spectrum tables. **Include later:** vector before/after along eigenlines, diagonalization change-of-basis pipeline. **Omit:** differential-equation and Markov-chain applications. |
| 09 Orthogonality | Inner-product interpretation, norm/angle, complements, projection, residual, least-squares choice, Gram-Schmidt, QR, exact-versus-approximate fit. | Possible: compact projection or normal-equation relation only after derivation; no procedural prose clozes. | Analyzed projection → completion orthogonalization → faded QR → independent least squares → mixed exact solve/projection/least-squares choice. | Dot-product tables, right-angle geometry, residual diagrams, orthonormal columns. **Include later:** projection/residual, Gram-Schmidt before/after, QR column geometry. **Omit:** statistical regression claims and data interpretation. |
| 10 Duality/tensors | Functional evaluation, dual basis, coordinate transformation laws, bilinear/quadratic classification, tensor input/output arity, determinant as alternating form. | Possible: short notation for dual basis or tensor product after meaning; zero clozes is acceptable because variance conventions demand reasoning. | Analyzed functional → completion dual basis → faded bilinear coordinate change → independent tensor-product interpretation → mixed vector/covector/form/tensor discrimination. | Covector level sets, matrices of forms, multilinear input-output diagrams, index arrays. **Include later:** functional parallel-level-set picture, dual-basis pairing grid, tensor wiring/arity diagram. **Omit:** tensor calculus, manifolds, Einstein summation until explicitly established. |
| 11 Spectral/SVD | Symmetric/Hermitian tests, positivity, spectral hypotheses, singular directions/values, pseudoinverse, low-rank approximation, matrix-norm meaning, factorization selection. | Possible: factorization names or compact identities after conceptual contrasts; theorem hypotheses should be retrieved with conditions, not slogan clozes. | Analyzed symmetric spectral geometry → completion singular-value step → faded SVD reconstruction → independent pseudoinverse/low-rank decision → mixed LU/QR/eigen/SVD selection. | Orthogonal axes, unit circle/sphere to ellipse/ellipsoid, factorization chains, singular-value tables. **Include later:** spectral axes, SVD geometry, rank-`k` approximation sequence, factorization-purpose map. **Omit:** production compression datasets and numerical error claims. |

## Pilot chapter 01 pre-authoring ledger

This ledger freezes the build before card authoring. The pilot uses only the
validator-resolved inbound capabilities named above. It does not assume the
unscheduled algebra chapters on systems, coordinate planes, lines, functions,
or polynomial expressions.

### Retrieval and card-form plan

| Front order | Stable card ID | Retrieval target | Planned form and role |
|---:|---|---|---|
| 1 | `aafa6b16-5328-459a-bdaf-1dd5bc51d152` | Interpret two equations required simultaneously. | `Q:/A:` minimal teaching bridge and bounded inference. |
| 2 | `c4bd6239-b161-43f9-b605-f68c83c5fbb0` | Recognize the locally defined form of a linear equation. | `Q:/A:` operational definition and discrimination. |
| 3 | `41008c2c-81a2-4c09-935f-1cf00a05e5f7` | State when values solve a linear system. | `Q:/A:` supported definition retrieval. |
| 4 | `46faa379-70c9-4796-9da7-d702f891aa75` | Encode variable values in an ordered solution tuple. | `Q:/A:` notation bridge and translation. |
| 5 | `fa5056f3-1dff-4a2b-8c80-0649c3c34344` | Check a proposed tuple against every equation. | `Q:/A:` varied application and misconception repair. |
| 6 | `43a2b6b5-d513-4ccc-a4ad-abfb9b41b8ac` | Interpret rows, columns, brackets, and the augmentation bar. | `Q:/A:` representation bridge. |
| 7 | `a1715ef3-92e4-4070-b50c-7b5a25338280` | Translate equations to an augmented matrix. | `Q:/A:` symbolic-to-array translation. |
| 8 | `d94d40ec-df51-40e3-8391-a317e75ff68a` | Translate an augmented matrix back to equations. | `Q:/A:` reverse translation. |
| 9 | `030f55d1-4652-4e87-9876-2023913255b6` | Explain why swapping rows preserves solutions. | `Q:/A:` first reversible operation. |
| 10 | `cdea1488-87fa-488b-b194-bcc35c7ef19d` | Explain why row scaling requires a nonzero number. | `Q:/A:` boundary condition and error diagnosis. |
| 11 | `e9410163-68c4-4965-a160-a2240d261ebe` | Explain why row replacement preserves solutions. | `Q:/A:` reversible-operation reasoning. |
| 12 | `56abea86-58ce-4268-a3bb-d1a830c676db` | Recall the complete elementary-row-operation set. | `Q:/A:` bounded three-part procedure inventory. |
| 13 | `36bc1d25-12f9-4270-a872-490655481662` | Connect row equivalence to an unchanged solution set. | `Q:/A:` governing invariant. |
| 14 | `774fbcbe-967e-4787-aaaf-a6c4ed362895` | Choose and execute one eliminating row replacement. | `P:/S:` analyzed first problem with full IPEE support. |
| 15 | `a58e7ac9-d677-4fda-9aac-100adc2e008d` | Locate a row's leading entry. | `Q:/A:` vocabulary bridge. |
| 16 | `9aa1a776-94f2-453b-ae03-877e5e453a38` | Recognize a zero row and diagnose a violated echelon-form condition. | `Q:/A:` supported structural discrimination. |
| 17 | `07cc2c26-8bda-4586-9339-43c418a45561` | Distinguish reduced echelon form from echelon form. | `Q:/A:` neighboring-form contrast. |
| 18 | `1ae77cc1-a2d5-46c5-a39e-cab0e409275f` | Classify pivot and free variables. | `Q:/A:` notation-free structural interpretation. |
| 19 | `f5cfb904-2b69-4e17-a28e-d5c98aeb2c66` | Detect inconsistency from a contradiction row. | `Q:/A:` condition and error diagnosis. |
| 20 | `94630305-24b2-4691-972d-228f465f27c7` | Use free variables to distinguish unique from infinite solutions. | `Q:/A:` solution-case discrimination. |
| 21 | `5d387a4c-7fa9-440e-8581-d8513558f8b7` | Introduce a parameter and write all solution tuples. | `Q:/A:` parametric-representation bridge. |
| 22 | `624e45a6-404b-410c-9225-ee9dd65bd2f5` | State the Gaussian-elimination workflow and invariant. | `Q:/A:` method-selection and justification. |
| 23 | `c57c2f83-581f-4259-b3c4-f42d43bb2e76` | Read pivots, a free variable, and a parametrization from RREF. | `P:/S:` completion/faded interpretation with full IPEE. |
| 24 | `41e066d3-fc37-4243-a32f-620ed132dfe2` | Solve a small system independently by elimination. | `P:/S:` independent execution with substitution check. |
| 25 | `678357f5-ffbb-4fe0-b8f1-f225553d0322` | Classify a system with a contradiction as having no solution. | `P:/S:` independent case classification. |
| 26 | `695ed977-e266-4f3b-85da-0fb96e40af16` | Parametrize an infinite solution set after a zero row appears. | `P:/S:` independent parametrization. |
| 27 | `fa06f1b1-8509-408f-8ebb-b80210f0696d` | Give contradiction priority over the presence of a free variable. | `P:/S:` mixed-case discrimination. |

No cloze is planned: every candidate term or condition is better graded through
an explanation, representation decision, or structural diagnosis. Problems
progress from an analyzed single operation through RREF reading, an independent
solve, separate no-solution and infinite-solution cases, and a final mixed
discrimination.

### Pilot concept-dependency ledger

| Concept, symbol, representation, or procedure | Required on first front | Allowed inbound source or first establishment | First supported retrieval | Later application | Status |
|---|---:|---|---|---|---|
| Equation, variable, coefficient, constant, substitution, equality-preserving rewrite | 1 | Inbound from scheduled algebra capability summaries. | 1–3 | Throughout | ready |
| Simultaneous requirements | 1 | Minimally explained on front 1 using two inbound equations. | 1 | 3, 5 and all problems | ready |
| Linear equation in two variables; fixed-number coefficient form | 2 | Minimally defined on front 2 using inbound variables, coefficients, sums, and equality. | 2 | 3, 7–8 and all problems | ready |
| Linear system and system solution | 3 | Minimally defined on front 3 from fronts 1–2. | 3 | 5 and all later system work | ready |
| Ordered tuple and `(x,y)` position convention | 4 | Minimally explained on front 4 using established variable values. | 4 | 5, 21, 23–26 | ready |
| Augmented matrix; brackets, row, column, entry, augmentation bar | 6 | Minimally explained on front 6 from an established system. | 6–8 | 9–20 and 22–27 | ready |
| Coefficient/constant placement in an augmented matrix | 6 | Front 6 bridge. | 6–8 | All elimination problems | ready |
| Row swap | 9 | Explained on front 9 as exchanging equation order. | 9, 12 | 13–14 and 22–27 | ready |
| Row scaling by a nonzero number | 10 | Explained on front 10 from equality-preserving multiplication and reversibility. | 10, 12 | 13–14 and 22–27 | ready |
| Row replacement by adding a multiple of another row | 11 | Explained on front 11 with its reversing subtraction. | 11–12 | 13–14 and 22–27 | ready |
| Elementary row operation | 12 | Collective name applied after all three operations are established. | 12 | 13–14 and 22–27 | ready |
| Row-equivalent matrices and solution-set invariance | 13 | Defined and justified on front 13 from reversible row operations. | 13 | 14 and 22–27 | ready |
| Solution set | 13 | Defined on front 13 as the collection of all solution tuples. | 13 | 20–27 | ready |
| Replacement notation `row 2 ← row 2 - 2(row 1)` | 14 | Minimally decoded on problem front 14 using established row replacement. | 14 | 22–27 | ready |
| Leading entry | 15 | Minimally defined on front 15 using established rows and entries. | 15 | 16–20 and 23–27 | ready |
| Zero row and echelon form | 16 | Zero row and the three echelon conditions are stated on front 16 using front 15. | 16 | 17–20 and 22–27 | ready |
| Reduced row echelon form (RREF) | 17 | Extra leading-one and pivot-column conditions stated on front 17. | 17 | 18–21 and 23, 27 | ready |
| Pivot position, pivot variable, free variable | 18 | Defined on front 18 from established RREF and variable columns. | 18 | 20–21, 23, 26–27 | ready |
| Consistent, inconsistent, contradiction row | 19 | Defined on front 19; `0=1` is interpreted with inbound equality. | 19 | 20 and 25–27 | ready |
| Real-number domain | 20 | Minimally bridged on front 20 as values represented on the usual number line. | 20 | 21, 23, 26 | ready |
| Unique, none, or infinitely many solutions | 19 | No-solution case established on 19; consistent cases contrasted on 20. | 19–20 | 23–27 | ready |
| Parameter `t` and parametric description | 21 | Minimally explained and worked on front 21 after free variables and tuples. | 21 | 23 and 26 | ready |
| Gaussian elimination and back-substitution | 22 | Workflow minimally explained on front 22 from established row operations and echelon form. | 22 | 24–26 | ready |

### Authentic representations and figure decisions

- **Included representations:** equation systems, ordered solution tuples,
  augmented arrays, verbal row-operation descriptions, row-replacement
  notation, echelon/RREF arrays, and parametric tuples.
- **Solution-set intersection sketch: omitted for the pilot.** Coordinate axes,
  equation graphs, and line grammar are not inbound; teaching them here would
  create a separate dependency chain without improving elimination retrieval.
- **Before/after row-operation figure: omitted.** The exact augmented arrays and
  operation notation are the authentic representation; a separate diagram
  would duplicate the same decision rather than add spatial retrieval.
- **Solution-case decision tree: omitted.** It would expose the classification
  logic on a front or become a decorative answer summary. The mixed final
  problem retrieves that logic directly.

Planned inventory: 27 cards (`Q:/A:` 21, `P:/S:` 6, `C:` 0); six problems in
the progression above; zero figures, with all identified opportunities
intentionally omitted for prerequisite or retrieval-role reasons.

Actual pilot inventory: 27 cards (`Q:/A:` 21, `P:/S:` 6, `C:` 0); all six
planned problem stages are present; zero figures. During the first-use repair,
zero-row recognition moved from the leading-entry bridge to the following
echelon diagnosis so each front retains one grading decision; no target was
omitted. The detailed reconciliation is in
`.flashcards/audits/pilot-cold-start.md`.

## Chapter 02 pre-authoring ledger

This ledger freezes the chapter boundary before card authoring. The only local
inbound chapter is `01_linear_systems_and_elimination`; the external frontier is
limited to the validator-resolved scheduled arithmetic and elementary-algebra
capabilities recorded above. Coordinate-plane, line, function, matrix-product,
subspace, independence, basis, and later terminology are not inbound.

### Retrieval and card-form plan

| Front order | Stable card ID | Retrieval target | Planned form and role |
|---:|---|---|---|
| 1 | `25347fc5-339e-4f47-8556-936ba86f0bf7` | Interpret a coordinate vector and the column convention. | `Q:/A:` minimal representation bridge and bounded inference. |
| 2 | `cc365f12-37ca-444b-a29c-b7654c00661c` | Decide equality of coordinate vectors entry by entry. | `Q:/A:` operational definition and boundary condition. |
| 3 | `802f1984-daa4-4814-b709-086344e0df21` | Add equal-length coordinate vectors. | `Q:/A:` minimally explained operation and supported computation. |
| 4 | `287963aa-6e76-466c-a461-180201990b6c` | Diagnose why unequal-length vectors cannot be added here. | `Q:/A:` error diagnosis. |
| 5 | `b16dbef4-b4ee-4a2c-a4d0-d4b3bd798e3f` | Interpret a scalar and compute scalar multiplication. | `Q:/A:` term bridge and supported computation. |
| 6 | `8d83336b-5f61-462e-9613-9ac2caa52c97` | Identify the zero vector of a required length by its additive role. | `Q:/A:` definition and identity reasoning. |
| 7 | `73142b11-a6ad-4b7d-90b6-341a68dc2c5b` | Translate a two-entry column vector to an arrow on newly bridged coordinate axes. | `Q:/A:` verbal-symbolic-spatial grammar bridge. |
| 8 | `f63ba28c-c25d-48d0-9537-1ddf6cba08e7` | Interpret vector addition by a head-to-tail diagram. | `Q:/A:` figure-based representation translation. |
| 9 | `acea6ebe-e046-447e-afb6-f10126e7561c` | Infer a negative scalar from reversed direction and doubled coordinates. | `Q:/A:` figure-based qualitative and quantitative interpretation. |
| 10 | `18ce3653-35fa-46bf-9a90-4731c4937ecd` | Execute a mixed scalar-multiplication and vector-addition calculation. | `P:/S:` analyzed operation problem with full IPEE. |
| 11 | `d38c064a-0451-43c4-96e4-43cf90365c9a` | Recognize the defining structure of a linear combination. | `Q:/A:` supported definition retrieval. |
| 12 | `c82a0011-56fa-4bfd-b141-9140b8b3abf5` | Compute a linear combination of two coordinate vectors. | `P:/S:` completion problem with full IPEE. |
| 13 | `c583b0ee-759b-45c9-988a-7ee62ffeefaa` | Translate a vector equation into simultaneous coordinate equations. | `Q:/A:` symbolic-to-system bridge. |
| 14 | `7a060c55-f15b-4200-8218-621def98e783` | Solve a vector equation by the established linear-system method. | `P:/S:` analyzed translation and solve. |
| 15 | `7e0fe0c9-32f9-4e88-8f16-30b8ce96df37` | Interpret span as the collection of all linear combinations. | `Q:/A:` minimal definition and membership certificate. |
| 16 | `b1b4402a-20b9-4f16-a7b5-e493c1db276a` | Explain why every span contains the zero vector. | `Q:/A:` structural consequence and check. |
| 17 | `83da928a-1e06-424c-86a9-a9be3fd91da2` | Connect span membership to consistency of a coefficient system. | `Q:/A:` method-selection rule. |
| 18 | `da58b522-364e-40ac-a5e5-d78d6380fe16` | Certify span membership by finding coefficients. | `P:/S:` faded positive membership decision. |
| 19 | `39925a04-fd90-4fd1-b771-a074760ac474` | Reject span membership from a contradiction row. | `P:/S:` independent negative membership decision. |
| 20 | `7c4a7add-7232-4a1c-bc54-a4739f940a69` | Define a homogeneous linear system and infer its zero solution. | `Q:/A:` minimal bridge and supported inference. |
| 21 | `ce809411-1dab-4af5-be25-ae6a97a88eaf` | Parametrize a homogeneous system and rewrite its solutions as a span. | `P:/S:` mixed representation synthesis with full IPEE. |
| 22 | `19b93161-2c9b-4fe2-838d-a181e3b0b0e0` | Diagnose the use of a zero-target equation in a nonzero span-membership test. | `Q:/A:` vector-equation versus homogeneous-system discrimination. |
| 23 | `c2021da9-8e70-4d17-9e81-b6ef4dac36a3` | Reject the misconception that a span contains only its listed generators. | `Q:/A:` final mixed conceptual discrimination. |

No cloze is planned. Each exact symbol is introduced as part of a representation
or reasoning decision, so isolated deletion would grade notation more than
meaning. The six problems progress from analyzed vector arithmetic through a
completion linear combination, an analyzed vector-equation solve, faded and
independent span decisions, and a final homogeneous-system synthesis.

### Chapter 02 concept-dependency ledger

| Concept, symbol, representation, or procedure | Required on first front | Allowed inbound source or first establishment | First supported retrieval | Later application | Status |
|---|---:|---|---|---|---|
| Real numbers, ordered tuples/lists, entries, substitution, simultaneous equations, augmented matrices, consistency, contradiction rows, free variables, parameters, Gaussian elimination | 1 | Inbound from the resolved external capabilities and chapter 01 scheduled cards. | Chapter 01 | Throughout | ready |
| Coordinate vector and entry order | 1 | Minimally defined on front 1 as an ordered list of real numbers. | 1 | 2–23 | ready |
| Column-vector convention and bracket grammar | 1 | Front 1 states that this deck writes the ordered entries vertically. | 1 | 2–23 | ready |
| Vector equality and corresponding entries | 2 | Minimally defined on front 2 using established entry order. | 2 | 3–23 | ready |
| Vector addition and equal-length requirement | 3 | Front 3 defines addition entry by entry; front 4 isolates the length boundary. | 3–4 | 8, 10–23 | ready |
| Scalar and scalar multiplication | 5 | Front 5 defines a scalar as a real-number multiplier and defines entrywise scaling. | 5 | 9–23 | ready |
| Zero vector and additive identity role | 6 | Front 6 defines the all-zero vector of the required length and asks for its role. | 6 | 16, 20–23 | ready |
| Coordinate axes, origin, positive/negative direction, vector-as-arrow convention | 7 | Minimally explained on front 7 using number-line direction and two established entries. | 7 | Figures on 8–9 | ready |
| Head-to-tail diagram grammar and translated copy of an arrow | 8 | Front 8 describes the unchanged copied arrow and labels all endpoints. | 8 | No later front requires the diagram | ready |
| Direction and coordinate scaling in an arrow diagram | 9 | Front 9 supplies endpoint coordinates after fronts 5 and 7. | 9 | No later front requires the diagram | ready |
| Linear combination and coefficient | 11 | Front 11 defines the sum-of-scalar-multiples structure; `coefficient` is inbound algebra vocabulary and is applied to vector multipliers. | 11 | 12–23 | ready |
| Vector equation and unknown scalar coefficients | 13 | Front 13 defines the form and equates corresponding entries using fronts 2 and 11. | 13–14 | 15–22 | ready |
| Span and `span{...}` notation | 15 | Front 15 defines span as all linear combinations and introduces the notation in the same bridge. | 15 | 16–23 | ready |
| Span-membership certificate | 15 | A displayed set of coefficients witnesses membership on front 15. | 15 | 17–19, 22–23 | ready |
| Span-membership system test | 17 | Front 17 derives the test from the established vector equation and chapter 01 consistency. | 17 | 18–19, 22 | ready |
| Homogeneous linear system and zero solution | 20 | Front 20 defines zero right-side constants and asks for the resulting always-valid tuple. | 20 | 21–22 | ready |
| Parametric vector form of a homogeneous solution set | 21 | Problem front 21 requests only established elimination and span operations. | 21 | Downstream chapters | ready |

Rejected examples for this chapter: matrix-vector product notation, lines or
planes as already-known geometric objects, rotations, force or velocity models,
computer graphics, regression, independence, bases, subspaces, and null spaces.
They depend on later chapters, unscheduled external chapters, or undeclared
application knowledge and are unnecessary to the target decisions.

### Authentic representations and figure decisions

- **Included representations:** vertical coordinate lists, verbal entry rules,
  symbolic vector expressions, two-coordinate arrow diagrams, vector equations,
  coordinate equation systems, augmented matrices, parametric vectors, and span
  notation.
- **Head-to-tail addition figure: include.** It tests a spatial translation not
  recoverable from an array alone. The front supplies all endpoint and copied-
  arrow grammar without naming the sum arrow.
- **Signed scalar-multiple figure: include.** It separately tests direction
  reversal and coordinate scaling; endpoint coordinates make the task available
  without relying on color.
- **Coordinate-vector arrow figure: omit as a separate asset.** Front 7 can
  establish the complete convention in words and symbols; a second arrow-only
  picture would duplicate front 9 rather than add a decision.
- **Span-of-one/two-vectors region figure: omit.** Accurate interpretation would
  require line/plane and full coordinate-plane grammar that is not inbound or a
  declared chapter target. Algebraic coefficient systems provide the authentic
  membership representation at the current frontier.
- **Parallelogram variant: omit.** The head-to-tail diagram already retrieves
  the geometric addition rule; a second construction would be redundant here.

Planned inventory: 23 cards (`Q:/A:` 17, `P:/S:` 6, `C:` 0); six problems;
two TikZ/SVG figures with distinct retrieval roles.

Actual inventory: 23 cards (`Q:/A:` 17, `P:/S:` 6, `C:` 0); all six planned
problem roles and both planned figure roles are present. The cold-start repair
defined the membership symbol on front 15 and simplified fronts 16–17 from
general indexed lists to two-vector forms; neither change removed a retrieval
target. The detailed reconciliation is in
`.flashcards/audits/02_vectors_linear_combinations_and_span-cold-start.md`.

## Chapter 03 pre-authoring ledger

This ledger freezes the chapter boundary before card authoring. The only direct
local inbound chapter is `02_vectors_linear_combinations_and_span`; chapter 01
and the external decks contribute only their validator-resolved capabilities.
Functions, bases, subspaces, inverses, determinants, eigenstructure, inner
products, affine coordinates, and application-specific models are not inbound.

### Retrieval and card-form plan

| Front order | Stable card ID | Retrieval target | Planned form and role |
|---:|---|---|---|
| 1 | `71cc4ded-812a-4280-8275-442ceaf36bc1` | Interpret a matrix as a rectangular array and locate an entry by row and column. | `Q:/A:` minimal representation bridge. |
| 2 | `a935c1fe-cef4-41fb-8389-ca7ee6655bbe` | Read matrix shape and indexed-entry notation. | `Q:/A:` notation bridge and supported retrieval. |
| 3 | `e7c2dbb7-aed3-4a44-a794-489389c1bc16` | Decide matrix equality entry by entry. | `Q:/A:` operational boundary condition. |
| 4 | `b9752adf-6bb8-479c-b0b1-81618ba8f26f` | Add same-shape matrices entrywise. | `Q:/A:` supported computation. |
| 5 | `fb8e2aca-4231-4fba-8a1a-9b1de08eccdc` | Diagnose a matrix-addition shape mismatch. | `Q:/A:` error diagnosis. |
| 6 | `b2404271-ab23-4b1e-ba0c-a8b2cf6dbab5` | Compute a scalar multiple of a matrix. | `Q:/A:` transfer from established vector scaling. |
| 7 | `3e8a63c3-acec-4110-836e-e792fe07c379` | Interpret a matrix-vector product as a linear combination of columns. | `Q:/A:` definition bridge with a supported computation. |
| 8 | `ecb6e435-edea-4282-9780-52caffc67f6d` | Infer input and output lengths from matrix shape. | `Q:/A:` dimension compatibility. |
| 9 | `eabaa070-841b-44cd-a093-9ee4f2137658` | Compute one output entry by pairing a row with the input entries. | `Q:/A:` representation translation. |
| 10 | `bfdfba18-2077-482d-b75a-8e2f746c7d6c` | Compute a complete matrix-vector product. | `P:/S:` analyzed first problem with full IPEE. |
| 11 | `c43f24e5-41ca-429d-823d-a51be7b38340` | Translate `A x = b` among matrix, column-combination, and system forms. | `Q:/A:` bridge to established systems. |
| 12 | `3ed819fc-02a0-4759-8302-0305ddb33ad6` | Recognize an identity matrix and its unchanged-vector action. | `Q:/A:` definition and role. |
| 13 | `6e02f5fe-f7b9-4a13-8496-acab9ead944c` | Choose the identity-matrix size compatible with a vector. | `Q:/A:` size discrimination. |
| 14 | `d9ab5b86-6c61-473f-b59e-be3455eb4395` | Form a transpose by exchanging row and column positions. | `Q:/A:` definition and supported computation. |
| 15 | `a5b466c3-c0d3-4b62-b653-736254fd4614` | Predict the transposed shape from the row/column exchange. | `Q:/A:` structural consequence. |
| 16 | `98832dc8-6fd3-49ba-99a9-2f1039b8fe39` | Interpret coordinate-transformation input/output notation. | `Q:/A:` local bridge because functions are not inbound. |
| 17 | `c6bce4ef-51cc-4196-91f1-4b36bf98e6b7` | Interpret the two defining preservation rules for a linear coordinate transformation. | `Q:/A:` supported definition retrieval. |
| 18 | `c0cc2ac0-9478-4c09-b3b0-3ebb406074e7` | Verify addition preservation in a concrete matrix transformation. | `Q:/A:` varied numerical check. |
| 19 | `24a799fa-4f3f-4e1f-8e53-40bb43702313` | Explain why every rule `T(x)=A x` is linear. | `Q:/A:` governing column-combination argument. |
| 20 | `2d6f9ab8-83f2-422c-9871-d5d87fd5abbb` | Interpret a matrix product column by column and determine its shape. | `Q:/A:` definition bridge. |
| 21 | `ed265ae3-60c9-4c53-8140-e12a546a72d5` | Compute a matrix product from matrix-vector products. | `P:/S:` completion problem with full IPEE. |
| 22 | `d6ced76a-7aeb-44f9-943a-68b3077233d7` | Diagnose product compatibility and order. | `Q:/A:` dimension-mismatch discrimination. |
| 23 | `2cac6ed4-2562-408c-a6fe-975128ebe857` | Translate a two-stage transformation pipeline to the product in the correct order. | `Q:/A:` figure-based structural retrieval. |
| 24 | `710cde3e-8bf2-468b-bb4d-aa28ec8b4b8a` | Compute and check a composed coordinate transformation. | `P:/S:` faded composition problem with full IPEE. |
| 25 | `5b1a7a45-7421-4167-a086-640f04e34d63` | Construct a matrix from the outputs of the two special coordinate inputs. | `P:/S:` independent figure-to-symbol translation with full IPEE. |
| 26 | `731ba8cc-2c18-4ba7-a0c3-7fe44606cca8` | Reject the assumption that reversing matrix factors preserves a product. | `Q:/A:` final mixed misconception diagnosis. |

No cloze is planned. Each compact notation item participates in a reasoning or
representation decision, so deletion would grade symbols more than meaning.
The four problems progress from an analyzed matrix-vector calculation through a
completion matrix product, a faded composition, and independent matrix
construction from transformation data.

### Chapter 03 concept-dependency ledger

| Concept, symbol, representation, or procedure | Required on first front | Allowed inbound source or first establishment | First supported retrieval | Later application | Status |
|---|---:|---|---|---|---|
| Real scalars; rectangular arrays; rows, columns, entries; coordinate vectors; vector equality, addition, scaling, linear combinations; vector equations and systems | 1 | Inbound from the resolved external capabilities and chapters 01–02. | Chapters 01–02 | Throughout | ready |
| Matrix as a rectangular array | 1 | Front 1 defines the object using established array, row, column, and entry language. | 1 | 2–26 | ready |
| Matrix shape `m x n` and indexed entry `a_ij` | 2 | Front 2 explicitly states row-first shape and index order. | 2 | 3–26 | ready |
| Matrix equality | 3 | Front 3 defines equality by same shape and corresponding entries. | 3 | 4–26 | ready |
| Matrix addition and same-shape condition | 4 | Front 4 defines entrywise addition; front 5 isolates the boundary. | 4–5 | 19, 26 and downstream | ready |
| Scalar–matrix multiplication | 6 | Front 6 extends established scalar–vector multiplication entrywise. | 6 | 19 and downstream | ready |
| Matrix–vector product `A x` and column-combination interpretation | 7 | Front 7 defines the product from established linear combinations. | 7 | 8–26 | ready |
| Matrix–vector compatibility and output length | 8 | Front 8 derives both lengths from column count and column length. | 8 | 10–26 | ready |
| Row-by-input computation rule | 9 | Front 9 derives one entry from the already established column combination. | 9–10 | 18, 21, 24–26 | ready |
| Matrix equation `A x = b` | 11 | Front 11 equates it with an established vector equation and linear system. | 11 | 19 and downstream | ready |
| Identity matrix `I_n`, diagonal positions, and unchanged-vector action | 12 | Front 12 defines its entries and demonstrates its column-combination action. | 12–13 | 25–26 and downstream | ready |
| Transpose `A^T` and row/column exchange | 14 | Front 14 defines the position swap with a concrete matrix. | 14–15 | Downstream | ready |
| Coordinate transformation, input/output, `T(x)` notation | 16 | Front 16 defines the rule and notation using only coordinate vectors. | 16 | 17–25 | ready |
| Linear coordinate transformation | 17 | Front 17 states and interprets the addition and scaling preservation rules. | 17–19 | 23–25 and downstream | ready |
| Matrix product `AB`, factor order, and column construction | 20 | Front 20 defines `AB` as the matrix with columns `A` times the columns of `B`. | 20–22 | 23–26 | ready |
| Composition as applying one transformation and then another | 23 | Front 23 defines the two-stage pipeline in words and a diagram after both matrix transformations and products are established. | 23–24 | 26 and downstream | ready |
| Special inputs `[1,0]^T` and `[0,1]^T` select the first and second columns | 25 | The problem front explains that each input supplies the weights on the two columns; no basis terminology is used. | 25 | Downstream basis work | ready |
| Noncommutativity of matrix multiplication | 26 | Front 26 provides an explicit same-size pair after product order and composition are established. | 26 | Downstream | ready |

Rejected examples for this chapter: named functions from algebra, affine
translations, rotations described by trigonometry, computer-graphics pipelines,
Markov chains, regression, elementary matrices, inverses, determinants, bases,
subspaces, rank, and eigenvectors. They require unscheduled external knowledge,
later chapters, or application-specific bridges not needed for these targets.

### Authentic representations and figure decisions

- **Included representations:** rectangular arrays, indexed entries, columns as
  coordinate vectors, row computations, matrix equations, input/output notation,
  and sequential transformation products.
- **Composition-order pipeline: include.** A compact left-to-right diagram tests
  the structural translation from temporal order to the right-to-left product;
  it does not display the answer product.
- **Special-input transformation diagram: include.** Separate input and output
  coordinate-arrow panels make matrix construction a genuine spatial-to-symbolic
  translation without invoking the future term `basis`.
- **General before/after grid: omit.** It would require introducing image-grid
  conventions and could suggest unsupported claims about all points when the
  scheduled target is construction from two explicit input-output pairs.
- **Entrywise addition/scaling figures: omit.** Exact arrays are the authentic
  representation, and a diagram would duplicate rather than improve retrieval.
- **Transpose flip animation or figure: omit.** The indexed and concrete array
  prompts grade the row/column exchange more precisely without adding a spatial
  convention.

Planned inventory: 26 cards (`Q:/A:` 22, `P:/S:` 4, `C:` 0); four problems;
two TikZ/SVG figures with distinct retrieval roles.

Actual inventory: 26 cards (`Q:/A:` 22, `P:/S:` 4, `C:` 0); all four planned
problem roles and both planned figure roles are present. The cold-start repair
made the `\longmapsto` direction explicit on front 25 and replaced unexplained
`commute` terminology on front 26 with a direct factor-reversal diagnosis; no
retrieval target was omitted. The detailed reconciliation is in
`.flashcards/audits/03_matrices_and_coordinate_transformations-cold-start.md`.

## Initial-learning path

The pilot must begin at the card-backed algebra frontier, not at the planned
scope of the prerequisite deck. Its first scheduled front should orient the
learner to simultaneous constraints using only known equation/equivalence
language. A short linear sequence then establishes each system representation,
retrieves one supported relationship, varies the representation, and only then
asks for method selection or independent elimination. Coordinate axes, ordered
tuples, matrix brackets, row-operation notation, and parametric notation all
require their own first-use bridge before appearing in a prompt, distractor,
table, or alt text.

Later chapters repeat that pattern: concrete motivation → minimal definition or
analyzed example → supported retrieval → representation translation → error
diagnosis → faded application → mixed method choice. Theorems are split into
hypotheses/conclusion, decisive proof idea, boundary counterexample, and later
application rather than memorized line by line. Complex scalars are introduced
through a dedicated bridge before any front uses conjugation, Hermitian adjoints,
or complex eigenvectors.

Before authoring beyond chapter 1, complete a front-by-front cold-start
simulation and save it as `.flashcards/audits/pilot-cold-start.md`; obtain
explicit pilot approval. No later chapter is authorized by this plan.

## Figure policy

The chapter ledger inventories candidate figures by retrieval role. When a
later authoring job approves one, author technical figures in TikZ, compile them
to responsive SVG, and store source/output together under
`figures/NN_chapter/`, with shared style at `figures/tikz-style.tex`. Load the
style as `\\input{figures/tikz-style.tex}`. Front figures contain setup only;
answer-revealing annotations belong on the back. Every figure needs a tight
`viewBox`, meaningful title/description, phone-width legibility, high contrast,
and a cue beyond color.

The chapter 1 pilot intentionally creates no figure directories, TikZ, SVG, or
other assets because each identified opportunity is either blocked by unseen
coordinate/line grammar or duplicates exact array notation. Purely symbolic
identities, small arithmetic tables, and facts whose retrieval does not depend
on spatial/structural inspection remain omitted as figure targets.

## Sources and accuracy

The authoritative curricular and claim-verification sources, licenses/terms,
access dates, scope decisions, and uncertainty are recorded in `README.md`.
Each later chapter authoring run must verify its theorem statements, hypotheses,
conventions, and computations anew.

## Validation gate

For the chapter 1 pilot build:

1. Run stabilization and deterministic prerequisite/deck validation.
2. Confirm the resolved explicit dependency boundary and validate all scheduled
   card markup, math, identities, and IPEE structures.
3. Complete `.flashcards/audits/pilot-cold-start.md`, including the separate
   first-use scan and planned-versus-actual reconciliation.
4. Run `git diff --check`, review the complete diff, and stop for human review.

No later chapter may be authored until this pilot is explicitly approved.
