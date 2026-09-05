# Chapter 04 cold-start, first-use, and atomicity audit

Audited 2026-09-04 in the isolated Chapter 4 build workspace. The learner is a
motivated adult at the undergraduate-core destination. No tools are assumed.
This report audits only `04_subspaces_and_fundamental_spaces.md` and its one new
figure; prerequisite and later chapter files were not modified.

## Chapter-boundary dependency ledger

| Boundary class | Allowed knowledge | Evidence and decision |
|---|---|---|
| Direct local prerequisite | Matrix shape/entries, matrix and vector operations, matrix-vector products, transpose, matrix products, coordinate transformations, linearity, and composition | Complete scheduled Chapter 3 cards in the resolved graph; allowed. |
| Transitive local summaries | Systems, row operations/equivalence, echelon/RREF, pivots/free variables, consistency/parametrization; coordinate vectors, vector operations, zero vector, linear combinations, span, and homogeneous systems | Validator-resolved summaries for Chapters 1–2; allowed only as named. |
| Scheduled external frontier | Real-number arithmetic; variables, algebraic expressions/equations, substitution/evaluation, equivalent expressions, operation properties, distribution, like terms, simplification, equation solutions, equality properties, one-step equations, and checking | Staged number-sense closure and the scheduled Chapters 1–3 of elementary algebra; allowed only as named. |
| Explicitly not inbound | Coordinate-plane and line grammar, functions from the unscheduled algebra chapters, proof-deck methods, basis, independence, dimension, rank-nullity, inverses, determinants, eigenstructure, inner products, affine terminology, and applied models | Excluded from all fronts and examples. |
| Chapter edge | `chapter:03_matrices_and_coordinate_transformations` | Present in frontmatter and in `.flashcards/prerequisites/graph.json`; no new inbound edge proposed. |

Dependency codes used below: **I** = confirmed inbound boundary above; **E#** =
established and retrieved on an earlier Chapter 4 front; **B** = a minimal
self-contained bridge on the current front. The scan recorded each front's
dependencies before inspecting its answer.

## Front-by-front cold-start and atomicity scan

| # | Card ID | Dependencies and source | One-sentence minimum passing response | Atomicity decision |
|---:|---|---|---|---|
| 1 | `6a160e94-30fc-4057-bf53-b28abc52e7c0` | Coordinate vector, entry count, real number: I; `R^n`: B. | `R^3` contains all three-entry real coordinate vectors. | keep — one notation interpretation. |
| 2 | `7e53526c-f779-4395-849f-bca787f711ea` | Collection, addition, scaling, real number, matrix: I; real vector space and vector-as-member: B. | A matrix can be a vector when it is an object in such a collection. | keep — one classification after a minimal orientation. |
| 3 | `1af15620-0ddb-4748-ad57-fae8d586267d` | Vector space: E2; addition: I; additive closure: B. | The sum of two vectors in `V` must remain in `V`. | keep — one law. |
| 4 | `cb6b78d3-6bc2-4d6d-a904-b304ca4b0b36` | Vector space: E2; scalar multiplication: I; scalar closure: B. | Every real scalar multiple of a vector in `V` must remain in `V`. | keep — one law. |
| 5 | `2c9c0a1b-f1d6-4f30-af15-e831411f16ef` | Vector addition: I; commutative law: B. | `u+v=v+u`. | keep — one law. |
| 6 | `88909be1-3477-41db-b49a-32a3b513db5c` | Vector addition: I; associative law: B. | `(u+v)+w=u+(v+w)`. | keep — one law. |
| 7 | `d3bf97e1-9b3c-4b8c-b410-239dd70f6942` | Zero vector: I; additive identity: B. | `u+0=u`. | keep — one law. |
| 8 | `c66398b3-482c-4f8a-9649-bf720f065664` | Zero vector/scaling by `-1`: I; additive inverse: B. | `u+(-u)=0`. | keep — one law. |
| 9 | `e3e69540-c0aa-4ecf-ad93-3bb42ec9671b` | Scalar multiplication: I; scalar-one identity: B. | `1u=u`. | keep — one law. |
| 10 | `bb08101e-395b-4559-88f3-ae02f6eb7ba9` | Scalar multiplication and real products: I; nested-scaling law: B. | `a(bu)=(ab)u`. | keep — one law. |
| 11 | `85297eb8-8aa1-4bb8-aaa4-e5c542d77434` | Addition/scaling: I; vector-sum distributive law: B. | `a(u+v)=au+av`. | keep — one law. |
| 12 | `84353f87-7d4f-4501-b969-e225b8e8a692` | Scalar addition/scaling: I; scalar-sum distributive law: B. | `(a+b)u=au+bu`. | keep — one law. |
| 13 | `d26214af-79bb-4142-bf71-287e8a526316` | `R^n`: E1; vector-space laws: E2–E12; entrywise operations: I. | `R^n` is closed and satisfies every law entrywise. | keep — one synthesis after all parts. |
| 14 | `616bc192-7003-49c5-8ed6-35433c75709b` | Matrix shape/addition/scaling: I; vector-space laws: E2–E12. | Fixed-shape real matrices are closed and satisfy the laws entrywise. | keep — one varied classification. |
| 15 | `5459dac9-9358-4121-ab52-a084d442abef` | Collection/member language: E1–E2; membership symbol: B. | `w∈W` means that `w` belongs to `W`. | keep — one symbol. |
| 16 | `5e8ed881-98a1-4ac4-9cbc-a25351e952f8` | Membership: E15; subset symbol: B. | From `W⊆V` and `w∈W`, conclude `w∈V`. | keep — one relation. |
| 17 | `1cb301ab-cabc-45b7-b987-62604044ac5e` | Subset: E16; operations: I; inherited operations: B. | Addition in `W` is the same addition already used in `V`. | keep — one operation-sharing relation. |
| 18 | `c0c04658-f35f-4568-b52a-cd99e90a3190` | Vector space: E2–E14; subset: E16; inherited operations: E17; subspace: B. | A subspace is a contained vector space using the ambient operations. | keep — one definition assembled from retrieved parts. |
| 19 | `ffa71fff-9dbc-481a-9587-f9a6ddf0b522` | Subspace: E18; zero vector: I. | The ambient zero vector must belong to the subset. | keep — one test condition. |
| 20 | `cb103cd6-fabe-4da8-8136-acbec8ee71eb` | Subspace: E18; addition closure: E3. | The sum of any two members must remain in the subset. | keep — one test condition. |
| 21 | `3daf652f-8af3-4b3f-a265-8ffb0dd95fb5` | Subspace: E18; scalar closure: E4. | Every real scalar multiple of a member must remain in the subset. | keep — one test condition. |
| 22 | `bdc6976e-47e4-4925-917c-dd1505f8f12b` | Three test conditions: E19–E21; subspace test name: B. | Passing the three checks proves that the subset is a subspace. | keep — one method conclusion. |
| 23 | `c9fe5c20-88a6-4a18-9aa1-57591c1766bd` | Coordinates/homogeneous equation: I; `R^3`: E1; membership/subspace test: E15–E22. | `W` is a subspace because zero, sums, and scalar multiples preserve `x+y-z=0`. | keep — one integrated classification whose method requires the three established checks. |
| 24 | `d76c4306-4bde-4545-b5e4-8a07bf4a17b7` | Span/linear combinations: I; subspace test: E19–E22. | A span passes all three checks because linear combinations remain linear combinations. | keep — one theorem reason after its parts. |
| 25 | `053b7d30-e6d9-4307-9f02-3e5c1e33a70a` | Zero vector: I; subspace test: E19–E22. | `{0}` is a subspace because its operations always return zero. | keep — one boundary classification. |
| 26 | `a5d8d561-a281-405f-9606-1604945e5029` | Two-entry vectors/scaling: I; failed universal condition: B; scalar closure: E21. | For example, `[1,0]` belongs but `2[1,0]=[2,0]` does not. | keep — one counterexample certificate. |
| 27 | `1ee374d9-0a14-49fd-83c5-9bb5a036f488` | Matrix equation/consistency/zero vector: I; zero test: E19. | The zero-vector condition fails because `A0=0≠b`. | keep — one decisive diagnosis. |
| 28 | `eef0e657-488c-4c90-9644-51a75a9bbb52` | Matrix inputs and zero output: I; membership: E15; null space and `N(A)`: B. | `x∈N(A)` exactly when `Ax=0`. | keep — one definition. |
| 29 | `a2aeebde-9fa8-42cf-8b32-344919104b54` | Matrix shape/input length: I; `R^n`: E1; null space: E28. | `N(A)⊆R^n` because its members are `n`-entry inputs. | keep — one ambient-space decision. |
| 30 | `b18e96d2-ac1e-4ab0-8af1-02a98950741f` | Null space: E28; zero test: E19; `A0=0`: I. | Zero belongs to `N(A)` because `A0=0`. | keep — one proof component. |
| 31 | `3f1a92c4-cf81-4946-a3e1-5305640ffa2a` | Null space: E28; linear transformation addition rule: I. | `A(u+v)=Au+Av=0`, so the sum remains in `N(A)`. | keep — one proof component. |
| 32 | `a9739f29-7bf4-4299-ae6a-79a293e00c2d` | Null space: E28; linear transformation scaling rule: I. | `A(cu)=cAu=0`, so the multiple remains in `N(A)`. | keep — one proof component. |
| 33 | `fd38ee1f-9b15-43f4-bf53-e9b700e30113` | E28–E32 and subspace test E22. | Every null space is a subspace of its input space. | keep — one conclusion after separate proof components. |
| 34 | `748327c8-db25-4c5d-abf8-38e6e1cf790e` | Homogeneous-system elimination/parameters/span: I; null space: E28. | `N(A)=span{[-3,1,1]}`. | keep — one calculation with a multiplication check. |
| 35 | `19210856-f1fc-469b-a1a9-2a399f72035e` | Linear transformation/input/output: I; kernel and `ker(T)`: B. | If `T(u)=0`, then `u∈ker(T)`. | keep — one definition application. |
| 36 | `21d8cc66-6095-4db2-845c-5352286765f1` | Matrix transformation: I; kernel E35; null space E28. | For `T(x)=Ax`, `ker(T)=N(A)`. | keep — one representation equality. |
| 37 | `2a9f4a5f-c3d5-4992-9667-02f49230c4b8` | Matrix columns/span: I; column space and `Col(A)`: B. | A column-space member is a linear combination of columns of `A`. | keep — one definition. |
| 38 | `76c42353-2942-469e-862c-881a8678a528` | Matrix shape/column length: I; `R^m`: E1; column space: E37. | `Col(A)⊆R^m` because the columns have `m` entries. | keep — one ambient-space decision. |
| 39 | `2229f08c-c20e-4d30-a5e9-404ca76fb041` | Transformation inputs/outputs: I; image: B. | Every attainable output belongs to the image. | keep — one definition application. |
| 40 | `fbba2858-d2fa-467f-acc4-1c9c000b64e6` | Matrix-vector column combinations: I; image E39; column space E37. | For `T(x)=Ax`, `image(T)=Col(A)`. | keep — one representation equality. |
| 41 | `237fbfa4-8a5d-4326-8336-3c1604a45be1` | Matrix equation/consistency: I; column space E37. | `Ax=b` is consistent exactly when `b∈Col(A)`. | keep — one equivalence. |
| 42 | `ae540adf-683d-4a03-b8fd-01e677a57a0e` | Matrix-vector product/system solving: I; membership E15; column space E37–E41; coefficient certificate: span knowledge I. | `b∈Col(A)` with coefficients `(1,2)`. | keep — the certificate is the evidence for the single membership decision. |
| 43 | `f7bc2802-2c72-44b6-8885-69b4e9439367` | Column space E37; span-subspace result E24. | `Col(A)` is a subspace because it is a span. | keep — one theorem transfer. |
| 44 | `c286ac05-2be6-4fba-9bd6-6e9492625e11` | Matrix rows and coordinate vectors: I; span: I; row space and `Row(A)`: B. | A row-space member is a linear combination of rows of `A`. | keep — one definition. |
| 45 | `15e6daf3-b33c-4a45-b378-d7672dea7b06` | Transpose: I; row space E44; column space E37. | `Row(A)=Col(A^T)` because transpose turns rows into columns. | keep — one representation equality. |
| 46 | `b71eda23-d16e-45ec-a072-794d5ff35c3a` | Matrix shape/row length: I; `R^n`: E1; row space E44. | `Row(A)⊆R^n` because each row has `n` entries. | keep — one ambient-space decision. |
| 47 | `416605b2-2620-4482-993f-6e91af4ba79d` | Elementary row operations: I; row space E44. | Every new row is an old-row linear combination. | keep — one-way proof step only. |
| 48 | `653d1d9e-7016-488c-963f-ef407a0554b0` | Reversibility of row operations: I; subset E16; one-way step E47. | The reverse operation gives the reverse containment, hence equal row spaces. | keep — second proof step only. |
| 49 | `14243d00-e5d7-485d-b049-b3c5f087036d` | RREF/zero row/span: I; row space E44. | A zero row adds no new linear combination. | keep — one omission rule. |
| 50 | `557cbf6a-43d1-47e0-bec5-5566096d4ff5` | Row reduction/RREF/span: I; row preservation E47–E48; zero-row rule E49. | `Row(A)=span{[1,0,1],[0,1,1]}`. | keep — one row-space extraction. |
| 51 | `7dfedc32-5c99-4877-8bb7-912fad921262` | Transpose I; null space E28; left null space: B. | `y` is left-null exactly when `A^T y=0`. | keep — one definition. |
| 52 | `d624d7ad-67da-43cb-934b-574fba18a96f` | Transposed shape: I; `R^m`: E1; left null E51. | `N(A^T)⊆R^m` because `A^T` accepts `m`-entry inputs. | keep — one ambient-space decision. |
| 53 | `b1d130a2-642f-4ac9-a172-d8da0ac25d4c` | Transpose/homogeneous solve/span: I; left null E51–E52. | `N(A^T)=span{[-1,-1,1]}`. | keep — one calculation with multiplication check. |
| 54 | `e7576ebb-5f18-4b4a-8419-2ea007b1aa6d` | Matrix shape/input-output and transpose: I; diagram solid/dashed arrow grammar: B; null space E28–E29. | `N(A)` lives in the left `n`-entry panel. | keep — one figure location. |
| 55 | `7ff68399-5d3f-48ed-86f6-17979af4b9d8` | Figure grammar E54; row space E44–E46. | `Row(A)` lives in the left `n`-entry panel. | keep — one figure location. |
| 56 | `ca03e33c-2074-4a1a-aa40-64ce9da1262c` | Figure grammar E54; column space E37–E38. | `Col(A)` lives in the right `m`-entry panel. | keep — one figure location. |
| 57 | `32fae25a-af2a-4322-a081-ec8c1ff2d207` | Figure grammar E54; left null E51–E52. | `N(A^T)` lives in the right `m`-entry panel. | keep — one figure location. |
| 58 | `ae4de958-99e3-4aa6-9036-00095ed9d9d9` | Echelon form/pivot position: I; rank and notation: B. | If there are `r` pivots, `rank(A)=r`. | keep — one definition inference. |
| 59 | `ab7852fa-93f5-47a9-9d43-e13f036a9fee` | Echelon pivots: I; rank E58. | The rank is `2`. | keep — one supported computation. |
| 60 | `8cf924b9-7e5e-4e85-8ca5-5090e169b6df` | Row reduction/pivots: I; column space E37; original-column selection rule: B. | Select columns 1 and 3 from the original `A`. | keep — one source-matrix choice. |
| 61 | `12af5425-51c3-4093-98a1-67c0fac83777` | RREF/nonzero rows: I; rank E58. | The number of nonzero RREF rows equals rank. | keep — one count relation. |
| 62 | `fd864615-6c1d-483e-bffe-ce02f11b8bad` | Rank E58; pivot-column E60; nonzero-row E61. | Rank equals both established spanning-list counts. | keep — one comparison after both counts are known. |
| 63 | `0133ece1-70bf-464f-a24f-aa650c98ed69` | Matrix/RREF/pivots/span: I; column space E37; selection rule E60. | `Col(A)=span{[1,2,0],[2,4,1]}`. | keep — one column-space extraction; the prior two-space problem was split. |
| 64 | `a1668050-7b62-45ec-a0c8-4e049775e987` | Four individually retrieved spaces E28, E37, E44, E51 and locations E54–E57; collective term: B. | The listed spaces are the four fundamental spaces of `A`. | keep — one name for established members. |
| 65 | `336ba51b-af9d-48dd-ab5f-2fa5d53e0f80` | Kernel E35–E36; image E39–E40; input/output I. | Kernel/null space answers input-to-zero; image/column space answers attainable output. | keep — one explicit contrast relation. |

No front depends on an answer from the same or a later card. Answer inspection
after the front-only pass introduced no later-front vocabulary that lacked an
earlier establishment.

## Separate first-use scan

| First use | First front | Establishment result |
|---|---:|---|
| `R^n` | 1 | Defined from inbound coordinate vectors and real entries before reuse. |
| Real vector space; objects called vectors | 2 | Minimal orientation only; the ten laws are not bundled. |
| Additive closure, scalar closure, commutativity, associativity, zero identity, inverse, scalar identity, nested scaling, and both distributive laws | 3–12 | One law per scheduled front before synthesis on 13–14. |
| `∈`, `⊆`, inherited operations | 15–17 | One symbol or relation per front before `subspace`. |
| Subspace | 18 | Uses only the retrieved concepts on 2–17. |
| Three-condition subspace test | 19–22 | Conditions retrieved separately before the collective method name. |
| Failed universal condition as a disproof | 26 | Self-bridged in words; set-builder notation was removed from the front. |
| Null space and `N(A)` | 28 | Definition precedes location, proof, calculation, and kernel comparison. |
| Kernel and `ker(T)` | 35 | Definition precedes equality with `N(A)`. |
| Column space and `Col(A)` | 37 | Definition precedes location, image, and solvability. |
| Image | 39 | Definition precedes equality with `Col(A)`. |
| Row space and `Row(A)` | 44 | Definition precedes transpose/location and row-reduction use. |
| Left null space | 51 | Definition precedes location, calculation, and figure use. |
| Fundamental-space diagram grammar | 54 | Arrow directions and panel lengths are explained without answer labels. |
| Rank | 58 | Defined from inbound pivots before computation and spanning-count links. |
| Four fundamental spaces | 64 | Collective name appears after all four spaces are defined and located. |

First-use repairs made during the audit: membership notation was removed from
fronts 3–12 and delayed to front 15; set-builder notation was removed from front
26; the two prior figure prompts were split into four one-space decisions; and
the prior combined row/column extraction problem was replaced with a single
column-space extraction target.

## Atomicity challenge

`Bridge` marks every front that supplies a new definition, symbol, law, diagram
grammar, or procedure. `T5` marks the validator's five longest Chapter 4 basic
fronts. Length is used only for deterministic triage.

| Card ID | Trigger | New material supplied on front | Single retrieval decision and minimum pass | Decision |
|---|---|---|---|---|
| `6a160e94-30fc-4057-bf53-b28abc52e7c0` | Bridge | `R^n` notation only | Interpret `R^3` as all three-entry real vectors. | keep — one symbol. |
| `7e53526c-f779-4395-849f-bca787f711ea` | Bridge, T5 (33 words) | Real vector space orientation and vector-as-member | A matrix may count as a vector when it is an object of the collection. | keep — the laws are deliberately absent and sequenced next. |
| `1af15620-0ddb-4748-ad57-fae8d586267d` | Bridge | Additive closure | A sum remains in `V`. | keep — one law. |
| `cb6b78d3-6bc2-4d6d-a904-b304ca4b0b36` | Bridge | Scalar closure | A real scalar multiple remains in `V`. | keep — one law. |
| `2c9c0a1b-f1d6-4f30-af15-e831411f16ef` | Bridge | Commutative vector-addition law | State `u+v=v+u`. | keep — one law. |
| `88909be1-3477-41db-b49a-32a3b513db5c` | Bridge | Associative vector-addition law | State `(u+v)+w=u+(v+w)`. | keep — one law. |
| `d3bf97e1-9b3c-4b8c-b410-239dd70f6942` | Bridge | Zero-vector identity law | State `u+0=u`. | keep — one law. |
| `c66398b3-482c-4f8a-9649-bf720f065664` | Bridge | Additive-inverse law | State `u+(-u)=0`. | keep — one law. |
| `e3e69540-c0aa-4ecf-ad93-3bb42ec9671b` | Bridge | Scalar-one identity | State `1u=u`. | keep — one law. |
| `bb08101e-395b-4559-88f3-ae02f6eb7ba9` | Bridge | Associativity of scaling | State `a(bu)=(ab)u`. | keep — one law. |
| `85297eb8-8aa1-4bb8-aaa4-e5c542d77434` | Bridge | Distribution over vector addition | State `a(u+v)=au+av`. | keep — one law. |
| `84353f87-7d4f-4501-b969-e225b8e8a692` | Bridge | Distribution over scalar addition | State `(a+b)u=au+bu`. | keep — one law. |
| `5459dac9-9358-4121-ab52-a084d442abef` | Bridge | Membership symbol | Read `w∈W`. | keep — one symbol. |
| `5e8ed881-98a1-4ac4-9cbc-a25351e952f8` | Bridge | Subset symbol | Infer membership in `V`. | keep — one relation. |
| `1cb301ab-cabc-45b7-b987-62604044ac5e` | Bridge, T5 (28 words) | Inherited-operations relation | Use `V`'s addition inside `W`. | keep — addition is the only graded operation; scaling is already established context. |
| `c0c04658-f35f-4568-b52a-cd99e90a3190` | Bridge, T5 (28 words) | Subspace definition | State the contained-vector-space relationship. | keep — membership, subset, and inherited operations were retrieved separately. |
| `ffa71fff-9dbc-481a-9587-f9a6ddf0b522` | Bridge | Zero condition | Zero must belong to `W`. | keep — one condition. |
| `cb103cd6-fabe-4da8-8136-acbec8ee71eb` | Bridge | Addition condition | Sums of members remain in `W`. | keep — one condition. |
| `3daf652f-8af3-4b3f-a265-8ffb0dd95fb5` | Bridge | Scaling condition | Scalar multiples remain in `W`. | keep — one condition. |
| `bdc6976e-47e4-4925-917c-dd1505f8f12b` | Bridge | Collective name and conclusion of the subspace test | Passing the established checks proves subspace status. | keep — no new condition is supplied. |
| `a5d8d561-a281-405f-9606-1604945e5029` | T5 (31 words) | One-failed-case disproof cue | Exhibit `[1,0]` and scalar `2`. | keep — one certificate; set-builder notation was removed. |
| `eef0e657-488c-4c90-9644-51a75a9bbb52` | Bridge | Null-space name and notation | Membership means `Ax=0`. | keep — ambient length is a separate card. |
| `19210856-f1fc-469b-a1a9-2a399f72035e` | Bridge | Kernel name and notation | `T(u)=0` places `u` in the kernel. | keep — matrix equality follows later. |
| `21d8cc66-6095-4db2-845c-5352286765f1` | Bridge | Kernel/null representation relation | State `ker(T)=N(A)` for `T(x)=Ax`. | keep — one equality. |
| `2a9f4a5f-c3d5-4992-9667-02f49230c4b8` | Bridge | Column-space name and notation | A member is a column combination. | keep — ambient length is separate. |
| `2229f08c-c20e-4d30-a5e9-404ca76fb041` | Bridge | Image definition | A produced output belongs to the image. | keep — matrix equality follows later. |
| `fbba2858-d2fa-467f-acc4-1c9c000b64e6` | Bridge | Image/column-space relation | State `image(T)=Col(A)` for `T(x)=Ax`. | keep — one equality. |
| `237fbfa4-8a5d-4326-8336-3c1604a45be1` | Bridge | Column-space solvability rule | State the consistency/membership equivalence. | keep — one equivalence. |
| `c286ac05-2be6-4fba-9bd6-6e9492625e11` | Bridge | Row-space name and notation | A member is a row combination. | keep — transpose and location are separate. |
| `15e6daf3-b33c-4a45-b378-d7672dea7b06` | Bridge | Row/transpose-column relation | State `Row(A)=Col(A^T)`. | keep — one equality. |
| `416605b2-2620-4482-993f-6e91af4ba79d` | Bridge | One-way row-span argument | Every new row is an old-row combination. | keep — reverse containment is delayed. |
| `653d1d9e-7016-488c-963f-ef407a0554b0` | Bridge | Reverse-containment step | Reversibility gives equality of row spaces. | keep — one proof transition. |
| `14243d00-e5d7-485d-b049-b3c5f087036d` | Bridge | Zero-row omission rule | Zero contributes no new combinations. | keep — one method boundary. |
| `7dfedc32-5c99-4877-8bb7-912fad921262` | Bridge | Left-null name and notation | Membership means `A^T y=0`. | keep — ambient length is separate. |
| `e7576ebb-5f18-4b4a-8419-2ea007b1aa6d` | Bridge | Solid/dashed arrow and panel-length grammar | Locate only `N(A)` in the left panel. | keep — one figure label decision. |
| `ae4de958-99e3-4aa6-9036-00095ed9d9d9` | Bridge | Rank name and notation | Infer `rank(A)=r` from `r` pivots. | keep — one definition inference. |
| `8cf924b9-7e5e-4e85-8ca5-5090e169b6df` | Bridge, T5 (28 words) | Original-column selection rule | Choose columns 1 and 3 from `A`. | keep — one source-matrix decision. |
| `12af5425-51c3-4093-98a1-67c0fac83777` | Bridge | Nonzero-row count rule | Nonzero RREF rows count rank. | keep — one relation. |
| `a1668050-7b62-45ec-a0c8-4e049775e987` | Bridge | Collective term “four fundamental spaces” | Name the already listed quartet. | keep — the four members are supplied only as established context. |

All other basic fronts were also checked through the front-by-front table above;
each has one minimum response and no independently gradable supplied bundle.
All six problem fronts ask for one classification, membership decision, or
space calculation and retain complete `IDENTIFY → PLAN → EXECUTE → EVALUATE`
structure.

### Split and retirement decisions relative to the prior comparison baseline

- `e523b540-b8cd-4446-a2d0-312aea8f88e9` and
  `6f1e05d6-b4ac-4d02-96f2-a4d15f80d0ec` are retired: each prior target asked
  for two independently gradable spaces on one side of the diagram. Four new
  one-space figure cards replace them.
- `36048395-3336-46a4-a0d6-778ddc249d5a` is retired: the prior problem bundled
  row-space and column-space extraction. Row-space extraction remains on
  `557cbf6a-43d1-47e0-bec5-5566096d4ff5`; new card
  `0133ece1-70bf-464f-a24f-aa650c98ed69` independently extracts the column
  space.
- Existing IDs were retained where the core retrieval decision remains the
  same; newly separated decisions received new IDs so no prior schedule is
  assigned to materially new knowledge.

No unresolved bundled retrieval or supplied teaching load remains.

## Research and claim verification

Live checks were completed on 2026-09-04 and recorded in the deck source
register.

- David Austin, *Understanding Linear Algebra*, §3.5 “Subspaces”:
  <https://understandinglinearalgebra.org/sec-subspaces.html>. Authority/role:
  current open first-course text; checked column/null definitions, solvability,
  pivot-column selection, and rank. Terms: CC BY 4.0; consulted without copying.
- Rob Beezer, *A First Course in Linear Algebra*, “Subspaces” and “Four
  Subsets”: <https://linear.ups.edu/linear.ups.edu/html/section-S.html> and
  <https://linear.ups.edu/linear.ups.edu/html/section-FS.html>. Authority/role:
  open university-authored text; independently checked the ten vector-space
  laws, subspace test, and all four matrix spaces. Terms: GNU FDL; consulted
  without copying.
- MIT OpenCourseWare 18.06SC, “The Four Fundamental Subspaces”:
  <https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/pages/ax-b-and-the-four-subspaces/the-four-fundamental-subspaces/>.
  Authority/role: undergraduate MIT course materials; checked the four-space
  organization and input/output connection. Terms: CC BY-NC-SA 4.0 unless the
  page notes otherwise; consulted for verification only.

All card prose, examples, and the TikZ figure are original. No unstable or
contested claims are used. The chapter remains finite-dimensional and real;
dimension language and rank-nullity are intentionally deferred to Chapter 5.

## Planned-versus-actual reconciliation

| Inventory | Planned | Actual | Reconciliation |
|---|---:|---:|---|
| `Q:/A:` | 59 | 59 | All definition, law, relation, diagnosis, and figure targets are present. |
| `P:/S:` | 6 | 6 | Subspace proof; null calculation; column membership; row extraction; left-null calculation; column extraction. |
| `C:` | 0 | 0 | Exact symbols and laws are better graded by bounded explanations or equations. |
| Total cards | 65 | 65 | Derived from the independent retrieval ledger; no count target or cap was used. |
| TikZ/SVG figures | 1 | 1 | `fundamental_space_sides` supports four one-space location decisions. |

Compared with the superseded 30-target plan, the actual regeneration adds the
atomic vector-space-law sequence, notation and inherited-operation bridges,
separate subspace-test conditions, decomposed definition/location pairs, and
four one-space figure decisions. It removes the two paired figure targets and
the bundled row/column extraction target. No declared Chapter 4 capability is
omitted.

Figure opportunity reconciliation:

- Included the planned input/output-side map; its drawing uses compact local
  coordinates, a tight responsive `viewBox`, centered panels, high contrast,
  and solid/dashed arrow cues.
- Omitted the ambient-subspace sketch because it would import line/plane
  grammar; omitted a four-space Venn diagram because it would imply one shared
  ambient set; omitted row-reduction and point-cloud figures because exact
  matrices and the included map already carry those retrieval roles.

## Validation record

Integration verification: the full collection validator passes with all 141
cards, all prerequisite edges, all five figures, and zero parser, math, image,
identity, markup, or frontmatter errors. The isolated path-resolution warning
below was resolved by validation in the complete collection layout. The missing
shared TikZ style was restored and the four earlier-chapter SVGs recompiled and
visually checked; their flashcards were unchanged.

- `flashcards deck stabilize . --check`: pass; zero missing stable IDs.
- `flashcards deck render-figures .`: pass; one new SVG updated from TikZ.
- Figure inspection: pass at phone-width scale; title, description, `viewBox`,
  centering, arrow direction, and dashed redundant cue are present.
- `flashcards deck validate .`: all 91 scheduled cards visible in this bounded
  workspace parsed; zero parser warnings, KaTeX errors, image errors, identity
  errors, markup errors, cloze lints, or frontmatter lints. The command reports
  one isolated-workspace path error because it seeks the external algebra deck
  at an unavailable sibling collection path. The supplied machine-resolved
  graph and staged prerequisite closure were read completely and contain the
  declared edge; this environmental lookup does not leave a semantic chapter
  dependency unexplained.
- Six solutions start immediately with `IDENTIFY`, retain ordered `PLAN`,
  `EXECUTE`, and `EVALUATE`, and place the direct result first inside `EXECUTE`.

cold_start_status: pass
unresolved_dependencies: 0
atomicity_status: pass
unresolved_atomicity_findings: 0
