# Linear Algebra card blueprint

This file records retrieval decisions specific to this deck. It is a plan for
later pilot and chapter authoring, not lesson content. No card form, problem, or
figure described below is created by this curriculum run.

## Learner model

- Level: undergraduate-core, for a motivated adult self-learner working with
  spaced retrieval plus written practice.
- Confirmed mathematical prerequisites: scheduled cards in
  `mathematics/elementary-algebra-and-functions` establish variables,
  expressions, equality statements, substitution, evaluation, verbal
  translation, equivalence, operation properties, distribution, like terms,
  and simplification. Its systems, functions, coordinate-plane, line,
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

“Include” below means plan for later card authoring; this run creates no card or
asset. Every structured problem will retain all IPEE headings. Progressions are
targets, not quotas, and may be shortened when a decision is already secure.

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

This curriculum run intentionally creates no figure directories, TikZ, SVG, or
other assets. Purely symbolic identities, small arithmetic tables, and facts
whose retrieval does not depend on spatial/structural inspection are omitted as
figure targets.

## Sources and accuracy

The authoritative curricular sources, licenses/terms, access dates, scope
decisions, and uncertainty are recorded in `README.md`. Card authoring must
verify theorem statements, hypotheses, conventions, and computations anew.

## Validation gate

For this curriculum-only run:

1. Run deterministic prerequisite/deck validation.
2. Confirm an acyclic graph, unique chapter IDs/orders, resolved explicit
   dependencies, and zero scheduled cards in every chapter.
3. Run `git diff --check` and review the complete diff for content or asset
   changes.
4. Stop for human review.

For a later content run, also run stabilization, full validation, the pilot
cold-start audit, figure inspection, and planned-versus-actual inventory
reconciliation before handoff.
