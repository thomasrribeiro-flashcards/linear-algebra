# Chapter 03 cold-start audit

Audit date: 2026-09-01

Target: `flashcards/03_matrices_and_coordinate_transformations.md`

## Chapter-boundary dependency ledger

- Edge mode: explicit.
- Direct local prerequisite: `chapter:02_vectors_linear_combinations_and_span`.
- Transitive local prerequisite: chapter 01 capability summary for systems and
  elimination.
- External frontier: validator-resolved scheduled capabilities from
  `mathematics/elementary-algebra-and-functions` and
  `mathematics/number-sense-and-arithmetic` only.
- Tools: none.
- Confirmed inbound groups used here: real-number arithmetic and operation
  properties; variables, expressions, equations, substitution, and checking;
  rows, columns, entries, and rectangular augmented arrays; coordinate vectors
  in the column convention; vector equality, addition, scalar multiplication,
  zero vectors, linear combinations, vector equations, span, and linear-system
  translation.
- Excluded at this boundary: unscheduled algebra functions and lines; bases,
  subspaces, rank, inverses, determinants, eigenstructure, inner products;
  affine coordinates; calculus, probability, graphics, and data models.

The detailed new-concept establishment ledger and planned card/figure portfolio
are recorded in `CARD_README.md` under “Chapter 03 pre-authoring ledger.” No
inbound edge was added.

## Front-only cold-start scan

The scan below was recorded from an extraction that stopped at every `A:` or
`S:` marker. Answers and solution stages were reviewed only after these front
dependencies had been listed.

| Front | Card ID | Dependencies needed to parse and attempt the front | Resolution at first attempt |
|---:|---|---|---|
| 1 | `71cc4ded-812a-4280-8275-442ceaf36bc1` | Rectangular array, number, row, column, entry; new term `matrix`. | Array grammar is inbound from chapter 01; `matrix` is minimally defined on this front. |
| 2 | `a935c1fe-cef4-41fb-8389-ca7ee6655bbe` | Matrix; variables; row/column counts; new `shape`, `m x n`, and `a_ij` grammar. | Matrix is front 1; all new notation is decoded on this front with row first. |
| 3 | `e7c2dbb7-aed3-4a44-a794-489389c1bc16` | Matrix shape, corresponding entries, equality. | Shape is front 2, vector corresponding-entry equality is inbound, and matrix equality is defined on this front. |
| 4 | `b9752adf-6bb8-479c-b0b1-81618ba8f26f` | Same shape, corresponding entries, signed addition; new matrix addition. | Fronts 2–3 plus inbound arithmetic; operation is defined on this front. |
| 5 | `fb8e2aca-4231-4fba-8a1a-9b1de08eccdc` | Matrix addition and shape. | Established on fronts 2 and 4. |
| 6 | `b2404271-ab23-4b1e-ba0c-a8b2cf6dbab5` | Scalar, matrix entry, signed multiplication; new scalar–matrix multiplication. | Scalar/vector scaling and arithmetic are inbound; matrix operation is defined on this front. |
| 7 | `3e8a63c3-acec-4110-836e-e792fe07c379` | Matrix columns, coordinate vectors, scalars, linear combinations; new `A x` product notation. | Vector concepts are inbound; the matrix–vector product is explicitly defined and immediately used. |
| 8 | `ecb6e435-edea-4282-9780-52caffc67f6d` | Shape, columns as vectors, matrix–vector product, input/output as ordinary operation language. | Fronts 2 and 7; the prompt states the required relation through column weights. |
| 9 | `eabaa070-841b-44cd-a093-9ee4f2137658` | Matrix–vector product, rows, corresponding multiplication and addition; symbolic entries. | Product is front 7; the equivalent row computation is explained on this front. |
| 10 | `bfdfba18-2077-482d-b75a-8e2f746c7d6c` | Complete matrix–vector execution. | Fronts 7–9 supply definition, size rule, and computation method. |
| 11 | `c43f24e5-41ca-429d-823d-a51be7b38340` | Matrix–vector product, vector equation, simultaneous equations; new name `matrix equation`. | Product is front 7; vector-equation/system translation is inbound; the new name is attached to displayed `A x = b`. |
| 12 | `3ed819fc-02a0-4759-8302-0305ddb33ad6` | Matrix–vector product, row/column positions, zero and one; new main diagonal and identity matrix. | Main diagonal and `I_2` entries are explained on this front; product is established. |
| 13 | `6e02f5fe-f7b9-4a13-8496-acab9ead944c` | Identity matrix, input/output length rule. | Fronts 8 and 12. |
| 14 | `d9ab5b86-6c61-473f-b59e-be3455eb4395` | Matrix positions; new transpose name, superscript, and swap rule. | Every new transpose element is explicitly defined on this front. |
| 15 | `a5b466c3-c0d3-4b62-b653-736254fd4614` | Matrix shape and transpose rule. | Fronts 2 and 14. |
| 16 | `98832dc8-6fd3-49ba-99a9-2f1039b8fe39` | Coordinate vectors and substitution; new input/output rule, coordinate transformation, and `T(x)` notation. | Vector/substitution knowledge is inbound; the transformation language and notation are fully bridged on this front without assuming functions. |
| 17 | `c6bce4ef-51cc-4196-91f1-4b36bf98e6b7` | Coordinate transformation, vector addition, scalar multiplication; new technical meaning of linear. | Front 16 and inbound vector operations; both preservation conditions are stated before retrieval. |
| 18 | `c0cc2ac0-9478-4c09-b3b0-3ebb406074e7` | `T(x)` notation, matrix–vector calculation, vector addition, linearity comparison. | Fronts 7–9 and 16–17. |
| 19 | `24a799fa-4f3f-4e1f-8e53-40bb43702313` | Matrix–vector product as column combination and definition of linear transformation. | Fronts 7 and 17–18. |
| 20 | `2d6f9ab8-83f2-422c-9871-d5d87fd5abbb` | Matrix shape, columns, matrix–vector products, ordered list ellipsis; new matrix product. | Ellipsis/list grammar and vectors are inbound; fronts 2, 7–8 support the complete definition on this front. |
| 21 | `ed265ae3-60c9-4c53-8140-e12a546a72d5` | Matrix product and matrix–vector computation. | Fronts 9–10 and 20. |
| 22 | `d6ced76a-7aeb-44f9-943a-68b3077233d7` | Ordered factors, product compatibility, output shape. | Front 20 establishes factor order and the inner-size condition through allowed column inputs. |
| 23 | `2cac6ed4-2562-408c-a6fe-975128ebe857` | Coordinate transformations, first/then order, matrix product; pipeline box-and-arrow grammar. | Fronts 16–20; the prose and alt text state the left-to-right stage order, and the figure labels only setup information. |
| 24 | `710cde3e-8bf2-468b-bb4d-aa28ec8b4b8a` | Two-stage transformation order, product matrix, matrix–vector execution. | Fronts 20–23. |
| 25 | `5b1a7a45-7421-4167-a086-640f04e34d63` | Linear matrix transformation, coordinate arrows/axes, column weights, special input-output pairs, `longmapsto` figure grammar. | Coordinate-arrow grammar is inbound from chapter 02; fronts 7 and 16–19 support the method; the front explicitly decodes the figure arrow and column-selection rule. |
| 26 | `731ba8cc-2c18-4ba7-a0c3-7fe44606cca8` | Matrix products, factor reversal, corresponding-entry inequality, real-number multiplication order property. | Product/order are fronts 20–24; equality is front 3; real-number operation properties are external inbound; both products are supplied for diagnosis. |

## Separate first-use scan

| First-use item | First scheduled front | Establishment result |
|---|---:|---|
| Matrix and rectangular-array representation | 1 | Defined from inbound array grammar before retrieval. |
| Shape `m x n` and indexed entry `a_ij` | 2 | Row-first conventions explicitly decoded. |
| Matrix equality | 3 | Same-shape and corresponding-entry conditions stated. |
| Matrix addition | 4 | Same-shape entrywise operation stated before computation. |
| Scalar–matrix multiplication | 6 | Entrywise rule stated using inbound scalar multiplication. |
| Matrix–vector product `A x` | 7 | Defined as an established column linear combination. |
| Row computation for `A x` | 9 | Pair-multiply-add rule explained before retrieval. |
| Matrix equation | 11 | New name attached to an established vector-equation/system translation. |
| Main diagonal and identity matrix `I_n` | 12 | Position rule and unchanged-output role introduced together. |
| Transpose `A^T` | 14 | Index swap and concrete operation defined. |
| Coordinate transformation and `T(x)` | 16 | Input/output rule and notation defined locally; no function prerequisite assumed. |
| Linear coordinate transformation | 17 | Addition and scaling preservation stated before later use. |
| Matrix product `AB` | 20 | Column-by-column definition and size conditions stated. |
| Two-stage composition/order | 23 | Sequential pipeline is explained using established transformations and products. |
| `longmapsto` in special-input figure | 25 | Direction and panel roles are decoded on the same front. |
| Factor-order misconception | 26 | Wording avoids unexplained `commute`; explicit products support diagnosis. |

First-use scan result: no future-facing term, symbol, example, supplied premise,
alt text, or figure label remains unexplained on its first front.

## Answer, solution, and markup review

After the front-only record was complete, every answer and solution was checked
against its prompt. The numerical matrix–vector products, matrix products,
composition order, transpose, identity action, shape claims, and special-input
matrix construction are internally consistent. Every `P:/S:` block begins
immediately with **IDENTIFY** and retains the ordered **IDENTIFY → PLAN → EXECUTE
→ EVALUATE** sequence; each direct result is the first sentence in **EXECUTE**.
No `A:` or `S:` body begins with a bare number-and-period sequence. The two
figure fronts state their visual grammar and do not expose the requested result.

## Planned-versus-actual reconciliation

Planned and actual inventories agree: 26 cards, comprising 22 `Q:/A:` cards,
four `P:/S:` cards, zero clozes, and two TikZ/SVG figures. The four problems
occupy the planned progression: analyzed matrix–vector computation, completion
matrix multiplication, faded composition, and independent construction from
transformation data. Both planned figure roles are present; every intentionally
omitted figure opportunity remains omitted for the reasons recorded in
`CARD_README.md`. No unexplained omission was found.

The authored Chapter 03 figures compile successfully. The isolated baseline's
two Chapter 02 TikZ files also reference `figures/tikz-style.tex`, although that
shared source was absent from the baseline; rebuilding them with the reconstructed
style produces only generator-level arrow-coordinate differences. Their staged
SVGs were therefore preserved byte-for-byte, as required, rather than rewritten.

cold_start_status: pass
unresolved_dependencies: 0
