# Chapter 04 cold-start audit: subspaces and fundamental spaces

Audit date: 2026-09-03  
Edge mode: explicit  
Target: `flashcards/04_subspaces_and_fundamental_spaces.md`

## Chapter-boundary dependency ledger

| Boundary source | Established inbound knowledge used here | Excluded knowledge |
|---|---|---|
| `chapter:03_matrices_and_coordinate_transformations` (direct; complete scheduled cards) | Matrices and shape; row/column entries; matrix addition and scaling; matrix-vector products by columns and rows; matrix equations; identity and transpose; coordinate transformations, linearity, matrix products, and composition. | Subspaces, kernels, images, rank, bases, dimension, inverses, determinants, eigenstructure, inner products. |
| Chapters 01–02 (transitive; validator-resolved summaries) | Systems, solutions, augmented matrices, row operations and equivalence, echelon/RREF, pivots and free variables, consistency, parametrization, Gaussian elimination; coordinate vectors, vector addition/scaling, zero vector, linear combinations, vector equations, span, span membership, homogeneous systems. | Any vocabulary or representation not included in their declared `provides` lists. |
| `mathematics/elementary-algebra-and-functions` (scheduled capability summaries only) | Variables, expressions, equations, terms and coefficients, substitution/evaluation, equivalent expressions and operation properties, simplification, equation solutions, equality operations, one-step equations, and equation checking. | Unscheduled systems, functions, coordinate-plane, line, polynomial, rational, exponential, and logarithmic material. |
| `mathematics/number-sense-and-arithmetic` (validator-resolved transitive capabilities) | Real-number arithmetic prerequisites, signed arithmetic, fractions/decimals, operation order, and quantitative checking as needed for small calculations. | No additional domain vocabulary or tool use. |
| Assumed tools | None. | Software, graphing tools, computer algebra, and proof assistants. |

No inbound edge was added. Later chapter concepts—especially independence,
basis, dimension, rank-nullity, invertibility, determinants, eigenstructure, and
orthogonality—remain outside the frontier.

## Front-only cold-start scan

This table was recorded from a front-only extraction before the answer and
solution bodies were inspected for the audit. `F#` denotes an earlier scheduled
front in this chapter.

| Front | Required to parse and attempt | Allowed source or establishment | Finding |
|---:|---|---|---|
| 1 | Coordinate vectors, real scalars, addition/scaling; new `R^n` and real-vector-space laws | Inbound operations; notation and complete law groups are explained on F1 | ready |
| 2 | Fixed matrix shape, matrix addition/scaling, vector space | Chapter 03; vector space retrieved on F1 | ready |
| 3 | Collection membership; new subset symbol, ambient space, inherited operations, subspace | Subset and subspace relationship explained on F3 using F1 | ready |
| 4 | Operation, subset, subspace; new closure language and three-part test | F3; closure and all three checks explained on F4 | ready |
| 5 | Two-entry vectors, equations, zero, addition/scaling, subspace test | Inbound algebra/vector operations and F1–F4 | ready |
| 6 | Span, linear combinations, closure, subspace | Chapter 02 and F3–F4 | ready |
| 7 | Scalar multiplication, membership, subspace counterexample | Inbound vector scaling and F3–F4 | ready |
| 8 | Matrix equation, consistency, nonzero vector, input space, subspace zero test | Chapters 01–03 and F3–F4 | ready |
| 9 | Matrix shape and product, zero output; new `N(A)` and set-builder colon | Chapters 02–03; null-space notation and colon meaning explained on F9 | ready |
| 10 | Null space, subspace, matrix linearity | F9, F3–F4, and chapter 03 | ready |
| 11 | Null-space equation, elimination, free parameter, span | F9–F10 and chapters 01–02 | ready |
| 12 | Linear transformation and zero output; new kernel and `ker` notation | Chapter 03; kernel is defined on F12 and related to F9 | ready |
| 13 | Columns, span, matrix shape; new column space and `Col` notation | Chapters 02–03; column space explained on F13 | ready |
| 14 | Transformation outputs; new image and `im` notation; column space | Chapter 03, F13; image explained on F14 | ready |
| 15 | Consistency of `Ax=b`, column-space membership | Chapters 01–03 and F13–F14 | ready |
| 16 | Column-space membership and coefficient-system method | F13–F15 and inbound system solving | ready |
| 17 | Column space, span, subspace test | F13 and F3–F6 | ready |
| 18 | Rows as coordinate vectors, transpose, column space; new row space | Chapter 03, F13; row-space representation explained on F18 | ready |
| 19 | RREF, row operations, span, row space; row-span invariance | Inbound reduction and F18; reversibility/row-combination bridge is on F19 | ready |
| 20 | Transpose and null space; new left null space and its ambient length | Chapter 03 and F9; definition explained on F20 | ready |
| 21 | Left-null equation, homogeneous solving, parametric span | F20 and inbound elimination/span | ready |
| 22 | `m x n` input/output lengths, `A`/`A^T` arrows, blank-slot figure grammar, null/row spaces | Chapter 03, F9, F18; diagram grammar stated on F22 | ready |
| 23 | Same diagram grammar, column and left-null spaces | F22, F13, F20 | ready |
| 24 | Echelon form, valid row operations, pivots; new rank | Chapter 01; rank and invariant pivot count defined on F24 | ready |
| 25 | Rank and echelon-array reading | F24 and chapter 01 | ready |
| 26 | RREF pivot indices, column combinations, column space; original-column selection rule | Chapters 02–03, F13; reversible coefficient-relation bridge is on F26 | ready |
| 27 | Rank, original pivot columns, nonzero RREF rows, row/column spaces | F18–F19 and F24–F26 | ready |
| 28 | One reduction record, span notation, row/column selection procedures | F18–F19 and F24–F27 | ready |
| 29 | Null, column, row, and left-null spaces; new collective label | F9, F13, F18, F20; collective term retrieved on F29 | ready |
| 30 | Input sent to zero versus attainable output; kernel/null versus image/column | F9, F12–F15 | ready |

Front-only result: every required dependency is inbound, established earlier,
or minimally bridged on that front. No future-facing example or supplied
advanced premise remains.

## Separate first-use scan

This pass was performed only after the front-only table above was complete.

| First use | Establishment and later-use check | Result |
|---|---|---|
| `R^n` and real vector space (F1) | F1 states the operation closure and complete law groups before asking why coordinate vectors qualify; F2 varies the representation. | pass |
| Subset, ambient space, inherited operations, subspace (F3) | F3 defines the relationship; F4 retrieves the operational test before F5 applies it. | pass |
| Closure and subspace test (F4) | The front defines closure and names all three checks; F5–F8 vary positive and negative cases. | pass |
| Null space and `N(A)` (F9) | F9 defines the set, decodes the colon, and retrieves the input length; F10 retrieves the subspace reason before F11 computes. | pass |
| Kernel and `ker(T)` (F12) | Defined from zero outputs and connected to the established null space before later discrimination. | pass |
| Column space and `Col(A)` (F13) | Defined from inbound span/column language and located in the output space; F14–F17 retrieve image and solvability relationships before reuse. | pass |
| Image and `im(T)` (F14) | Defined as attainable outputs and immediately connected to column space; no earlier front assumes it. | pass |
| Row space and `Row(A)` (F18) | Defined from rows and transpose; F19 now places the row-operation invariance bridge on the scheduled front before computation. | pass |
| Left null space (F20) | Defined through the established transpose and null space before F21 computes it. | pass |
| Figure grammar (F22) | The front and alt text explain both ambient sides, arrow directions, and blank slots without revealing the requested spaces; F23 reuses the established grammar. | pass |
| Rank (F24) | Defined by pivot count; F25 retrieves it concretely before F26–F28 use it in spanning procedures. | pass |
| Original-pivot-column selection (F26) | F26 supplies the reversible coefficient-relation bridge; F27 retrieves the general rule and F28 applies it. | pass |
| Four fundamental spaces as a collective term (F29) | Each member was defined and retrieved separately before the collective label appears. | pass |

Answer bodies introduce no terminology later assumed on a front without an
inbound source or earlier scheduled establishment. All six solutions begin at
IDENTIFY, retain IDENTIFY → PLAN → EXECUTE → EVALUATE in order, and place the
direct result first inside EXECUTE. No answer or solution begins with a bare
number-and-period sequence.

## Planned-versus-actual reconciliation

| Inventory | Planned | Actual | Reconciliation |
|---|---:|---:|---|
| `Q:/A:` | 24 | 24 | All definition, relationship, discrimination, and figure targets present. |
| `P:/S:` | 6 | 6 | Analyzed subspace test; completion null space; faded column and row space; independent left null; mixed pivot/row selection. |
| `C:` | 0 | 0 | Exact notation is graded through meaning and use, so no cloze earned a separate scheduling decision. |
| Figure assets | 1 TikZ/SVG pair | 1 TikZ/SVG pair | The input/output map supports two distinct relational fronts; all planned omissions remain justified in `CARD_README.md`. |

The compiled SVG has a tight `viewBox`, centered local geometry, meaningful
title/description, high contrast, and a dashed reverse arrow as a cue beyond
color. Visual inspection at a phone-scale preview found all labels and blank
slots legible.

The parser/stable-ID checks report 30 chapter cards, no missing IDs, no parser
warnings, no KaTeX/image/identity/markup/cloze/frontmatter errors, and valid
generation provenance. Full deck validation remains nonzero for two bounded
workspace conditions outside chapter-04 content: the validator resolves the
external prerequisite through an unavailable sibling path instead of the
staged closure, and the pre-existing chapter-03 SVGs do not byte-match a fresh
render after the previously absent shared TikZ style was restored. Those
chapter-03 assets were not modified, as required by the write boundary.

cold_start_status: pass
unresolved_dependencies: 0
