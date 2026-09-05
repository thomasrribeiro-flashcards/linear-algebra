# Chapter 01 cold-start audit

Target: `flashcards/01_linear_systems_and_elimination.md`
Date: 2026-09-05

cold_start_status: pass
unresolved_dependencies: 0

## Scope and method

Build-mode chapter-boundary revision of the existing 27-card chapter. All 15 ordered staged context files and the complete vendored skill were read. Graph schema 2, explicit edge mode: no local prerequisites; only the two staged external decks and no assumed tools. No later chapter was used to supply a card prerequisite.

Pre-authoring plan: [design ledger](01_linear_systems_and_elimination-design.md). Its E1/E2/E3/N labels identify exact staged capability sources. The staged external chapters are explicitly validator-resolved summaries; no scheduled external bodies are present. No extra capability was inferred from unscheduled algebra chapters or from the graph manifest’s original file sizes.

The initial inventory was not treated as a cold-start pass. After drafting, `.flashcards/work/fronts-only.md` was read in full without answers. For each front, dependencies and first-use findings below were recorded before the separate answer review. The table concerns semantic readiness, not evidence of actual learner mastery. Each same-front bridge requires a bounded supported decision before later reuse.

## Chapter-boundary dependency ledger

| Boundary | Evidence | Disposition |
|---|---|---|
| Incoming elementary algebra | Staged algebra summaries 01, 02, 03; E1/E2/E3 in design ledger | Only listed expression, equality and one-step/checking capabilities allowed. |
| Incoming arithmetic | Staged arithmetic summaries 01–10; N in design ledger | Used subset explicitly listed in design; no geometric axes, calculus or tools inferred. |
| Local incoming chapters | graph.json: localChapters and directLocalChapters empty | No local chapter imported. |
| New prerequisite edges | None proposed or added | prerequisites remains []; deck prerequisites unchanged. |
| Outgoing simultaneous-linear-equations / linear-system | Fronts 1–5, 7 | Simultaneous truth and fixed coefficients taught before matrix encoding. |
| Outgoing linear-system-solution-tuple | 6–8, 34–38 | Fixed variable order and all-solutions coverage; no vector arithmetic claimed. |
| Outgoing augmented-matrix | 9–11 | Rows, columns, coefficients, constants, zero entries and augmentation bar. |
| Outgoing elementary-row-operation / row-equivalence | 12–18 | Three operations, nonzero restriction, unchanged source row, two-direction preservation. |
| Outgoing echelon-form / reduced-row-echelon-form | 19–23 | Leading entries, zero rows, staircase, normalization and cleared pivot columns. |
| Outgoing pivot-and-free-variable | 24, 27–29, 34–35 | Variable versus constant columns; operational free choices; no rank claim. |
| Outgoing linear-system-consistency | 25–29, 37, 39 | Witness, contradiction, echelon criterion and priority over free-column count. |
| Outgoing linear-system-parametrization | 30, 34–35, 38 | One or multiple freely chosen real parameters; satisfaction and completeness checks. |
| Outgoing gaussian-elimination | 17–18, 31–33, 36–38 | Cancel, swap, skip, back-substitute, and verify. |

## Front-by-front scan (answers hidden during dependency recording)

| Front / stable ID | Required concepts and their established source | Same-front bridge | First-use finding |
|---|---|---|---|
| 1 / `aafa6b16-5328-459a-bdaf-1dd5bc51d152` | E1: equations, variables, substitution; N: addition/subtraction | Explain simultaneous as required at the same time. | Only known equations and substitution; simultaneous is explained in ordinary language. |
| 2 / `c4bd6239-b161-43f9-b605-f68c83c5fbb0` | E1 coefficients, constants; E2 sums/equivalent expressions | Define a finite sum of fixed-number multiples of variables equalling a fixed number; two-variable notation. | Fixed coefficients and equality are inbound; the definition is on this front, not in ignored lesson prose. |
| 3 / `a6bd0e82-c154-42e8-89ba-4190ccd1e4d3` | N: signed/fraction number lines; E3 one-step equations | Name values anywhere on the number line real numbers, not just integers; retrieve an allowed fractional solution. | Real-number name is bridged through inbound number-line/fraction capability; integer exclusion is not assumed to exclude fractions. |
| 4 / `cf4704d3-0f9f-42c0-b04b-ae3e4c3961de` | 2 fixed-coefficient form; E1 multiplication of variables | No new concept: contrast fixed coefficients with a variable factor. | Variable multiplication is inbound expression grammar; the decisive fixed-versus-variable contrast was established on 2. |
| 5 / `41008c2c-81a2-4c09-935f-1cf00a05e5f7` | 1 simultaneous; 2 linear equation | Define a linear system as one or more linear equations imposed together. | Uses retrieved simultaneous and linear concepts; one-equation systems explicitly allowed. |
| 6 / `46faa379-70c9-4796-9da7-d702f891aa75` | E1 variable values; 5 solution | Show parentheses and commas, fixed variable order, and componentwise equality notation. | Parentheses, commas and tuple equality are explicitly decoded before the encoding task. |
| 7 / `fa5056f3-1dff-4a2b-8c80-0649c3c34344` | 5 system; 6 tuple; E1/E3 substitution/checking | No new concept; state variable order explicitly. | Variable order is explicit; no assumed coordinate-plane interpretation. |
| 8 / `1dfd6bea-cade-46f9-9fd0-62259d289aaf` | 5–7 solution and tuple | Define solution set as all solution tuples; ask for a missed tuple. | Collection-of-all meaning is bridged; a missed solution tests coverage, not formal set notation. |
| 9 / `43a2b6b5-d513-4ccc-a4ad-abfb9b41b8ac` | E1 coefficients/constants; 5 equation system; N array | Define matrix as bracketed rectangular number array, horizontal rows, vertical columns, entries and bar encoding equality. | Matrix grammar is a single representation bridge; coefficient example supports inferring the bar meaning. No matrix arithmetic appears. |
| 10 / `a1715ef3-92e4-4070-b50c-7b5a25338280` | 9 array grammar; E1 coefficients including implicit 1 and -1 | No new concept. | Uses array encoding after 9; omitted unit coefficients follow inbound expression simplification. |
| 11 / `d94d40ec-df51-40e3-8391-a317e75ff68a` | 9–10 fixed columns; E2 zero terms | No new concept; omitted variable is a zero coefficient. | Reverse translation exercises zero coefficients using known zero multiplication. |
| 12 / `030f55d1-4652-4e87-9876-2023913255b6` | 5 simultaneous solution; 9 rows | Explain row swap as exchanging equation order. | Row swap translates to known simultaneous requirements; no formal proof technique assumed. |
| 13 / `cdea1488-87fa-488b-b194-bcc35c7ef19d` | E3 equality multiplication/division; 9 rows | Explain scaling every entry and the need to undo a change. | Nonzero condition uses reversible equality multiplication; answer can illustrate lost information without contradiction terminology. |
| 14 / `e9410163-68c4-4965-a160-a2240d261ebe` | E2 distribute/combine; E3 equality; 5 simultaneous; 9 rows | Explain adding a multiple of one whole equation to another, leaving source unchanged; retrieve undoing it. | Both forward implication and reversing operation are available from equality/distribution; no vector addition of rows. |
| 15 / `56abea86-58ce-4268-a3bb-d1a830c676db` | 12 swap; 13 scaling; 14 replacement | Give elementary row operations as collective name only. | Collective name only; all three operations were explained and retrieved independently first. |
| 16 / `36bc1d25-12f9-4270-a872-490655481662` | 8 solution set; 12–15 reversible row operations | Define row-equivalent as connected by finitely many elementary operations. | Only row equivalence is new; solution set was separately introduced on 8. |
| 17 / `774fbcbe-967e-4787-aaaf-a6c4ed362895` | 9 array; 14 replacement; N/E2 entry arithmetic | Decode row 2 ← row 2 - 2(row 1); analyze first entry, ask for full result. | Arrow and row multiplier are decoded on the front; first-entry arithmetic analyzed before completion. |
| 18 / `a92d9ead-a9e9-4dd2-87bb-50af7388f59c` | 17 replacement notation/execution; E3 one-step equation | No new concept; completion problem with one missing multiplier. | The square is explicitly the missing number; known replacement acts on the constant too. |
| 19 / `a58e7ac9-d677-4fda-9aac-100adc2e008d` | 9 entries/rows; N zero | Define nonzero row and leftmost nonzero entry. | Nonzero row and leftmost entry are one linked selection rule; all array positions are established. |
| 20 / `9eba409d-2f4a-455b-9966-385eb254e28e` | 9–11 augmented equation encoding | Define zero row; retrieve meaning of 0=0. | Zero-row meaning is retrieved before it becomes an echelon condition or a premise for parametrization. |
| 21 / `9aa1a776-94f2-453b-ae03-877e5e453a38` | 19 leading entry; 20 zero row; 9 columns | State zero-row, staircase and below-leading-zero conditions as one form; test one violated condition. | Echelon definition uses only established entries/zero rows; one misplaced-row diagnosis. |
| 22 / `07cc2c26-8bda-4586-9339-43c418a45561` | 21 echelon; 19 leading entry | Define RREF through its two extra conditions; isolate a leading-2 defect. | The two RREF conditions are stated; example now has only the intended normalization defect. |
| 23 / `61d9e205-782e-46d1-bda7-d76b3219d3ea` | 21–22 echelon versus RREF | No new concept; leading ones alone are insufficient. | Distinct retrieval of the other RREF condition; no new vocabulary. |
| 24 / `1ae77cc1-a2d5-46c5-a39e-cab0e409275f` | 19 leading entry; 21 echelon; 9 variable/constant columns | Define pivot as echelon leading entry and its location; distinguish variable columns with/without pivots. | Pivot, its position and column are names for the same established leading-entry structure; classification concerns variable columns only. |
| 25 / `56d11469-d3ad-4573-a382-6ef4c9cbca7f` | 5–8 solution tuples and set; E3 substitution | Define consistent as having at least one solution; distinguish existence from uniqueness. | Consistency is introduced through a checked solution, not as a new premise on a classification card. |
| 26 / `f5cfb904-2b69-4e17-a28e-d5c98aeb2c66` | 25 consistency; 9–11 row encoding; E3 equality | Define inconsistent (no solution) and contradiction row (impossible equality). | No-solution/contradiction meanings are explicitly supplied using established equality and consistency. |
| 27 / `55d2ab92-bdb5-4b55-a466-14e41cd4ec83` | 3 real domain; 24 free/pivot; 25 consistent; E3 equality | Explain arbitrary free choices in a consistent RREF system and solve pivot variables; model subtracting y from x+y=5. | Arbitrary free choice is explained in an already introduced RREF/consistent system; subtracting y is modeled using inbound equality properties. |
| 28 / `94630305-24b2-4691-972d-228f465f27c7` | 3 reals; 24 pivots; 25–27 consistency and arbitrary choice | Clarify unique means exactly one and infinitely many means more than any fixed whole-number count; contrast no choices with arbitrary real choices. | Unique and infinitely-many counts are explicitly glossed; the distinction follows operational free-choice practice and established real values. No exactly-two-solutions premise assumed. |
| 29 / `3001b75a-b798-421a-8d4a-ea6e1bfafa4e` | 20 zero row; 21 echelon; 24 pivots; 25–28 solution cases | State the echelon no-contradiction consistency criterion, then require independent variable-column inspection. | No-contradiction echelon criterion is explicitly supplied; the target varies the zero-row/free-column distinction. |
| 30 / `5d387a4c-7fa9-440e-8581-d8513558f8b7` | 6 tuple convention; 27 dependent value from free choice; 3 reals | Define parameter and parametrization; one separately chosen symbol per free variable; model subtraction to isolate x. | Parameter and parametrization form one representation bridge; subtraction and tuple construction are explicit, before independent three-variable problems. |
| 31 / `624e45a6-404b-410c-9225-ee9dd65bd2f5` | 15–16 row equivalence; 21 echelon; 24 pivots; 26 contradiction; 30 parameters | Explain left-to-right elimination, skipping empty columns, then bottom-up substitution; name back-substitution. | Procedure steps use established swaps/replacement/echelon/free choices; back-substitution is named and explained here. |
| 32 / `7a53ead1-5493-4a1d-99b2-976088bce643` | 31 bottom-up method; E3 one-step solve; 11 decoding | Analyze last row y=2; complete x and verify original rows. | A one-step solve is analyzed before bottom-up completion; no unscheduled multi-step-equation algorithm is assumed. |
| 33 / `00aca5e5-442a-4c86-8314-b761e96311ca` | 12 swap; 19 leading entry; 21 echelon; 31 algorithm | No new concept; distinguish zero candidate entry from absence of a usable entry in its column. | Method choice uses earlier swap and elimination instructions; nonzero entry versus all-zero remaining column distinguished. |
| 34 / `c57c2f83-581f-4259-b3c4-f42d43bb2e76` | 2 any finite variables; 6 tuples; 22–24 RREF/pivots; 30 parameters | No new concept; only one requested result, all solution tuples. | Three variable names are ordinary variables; tuple grammar and finite-sum equations already generalize. No vector interpretation is used. |
| 35 / `e85b3451-394b-4daa-98c9-dc9818b29578` | 24 free columns; 30 separate parameters; 34 tuple construction | No new concept; vary from one free column to two. | Separate symbols s,t are ordinary parameters under 30; no independence or dimension terminology borrowed. |
| 36 / `41e066d3-fc37-4243-a32f-620ed132dfe2` | 10 array setup; 17–18 replacement; 31–32 solve/check | No new concept. | All setup, elimination, bottom-up solving and checks are previously established. |
| 37 / `678357f5-ffbb-4fe0-b8f1-f225553d0322` | 17–18 elimination; 26 contradiction; 28–29 cases | No new concept. | No-solution case uses contradiction and full-system reasoning, not an unexplained proportional-line picture. |
| 38 / `695ed977-e266-4f3b-85da-0fb96e40af16` | 17–18 elimination; 20 zero row; 24,27–30 free parameters | No new concept. | Zero-row interpretation and free-choice mechanism precede the all-solutions task. |
| 39 / `fa06f1b1-8509-408f-8ebb-b80210f0696d` | 22 RREF; 24 variable/constant pivots; 26 contradiction; 28 cases | No new concept; state variable order and do not supply the classification premise. | Both constant-pivot and nonpivot-variable cues established; no supplied conclusion leaks the classification. |

## Separate first-use scan — U11 / D8

This second pass inspected domain-bearing words, implied procedures, mathematical arrays, examples, supplied premises, and missing-value notation separately from answer quality. There are no images, alt texts or figure labels in the chapter.

| First occurrence | New meaning / symbol | Classification and supported retrieval before reuse |
|---|---|---|
| 1 | simultaneous | On-front ordinary-language bridge; retrieve 1, reuse 5. |
| 2 | linear equation; fixed-number coefficient form ax+by=c | E1/E2 plus on-front definition; retrieve 2, discriminate 4 before system definition 5. |
| 3 | real numbers | Number-line bridge and fractional solution retrieval; reused 27 onward. |
| 5 | linear system / system solution | Compose retrieved 1–2; retrieve 5 then vary 7. |
| 6 | ordered tuple; parentheses/commas; componentwise tuple equality | Explicit notation bridge, retrieval 6 then 7; extend to 3 entries on 34. |
| 8 | solution set | All-tuples explanation with missing-solution decision; reuse 16. |
| 9 | matrix, row, column, entry, brackets, augmented matrix/bar | One encoding grammar tied to known coefficients/equation; retrieve 9 then both translation directions 10–11. |
| 12–14 | swap, nonzero scaling, row replacement, preservation / reversing | Each operation explained and retrieved before collective recall 15 and row equivalence 16. |
| 15 | elementary row operation | Collective name for retrieved operations, not a new mechanism. |
| 16 | row-equivalent | One new relation based on existing solution set/operations; retrieve its invariant. |
| 17–18 | replacement arrow, multiplier notation, missing-number square | Explicitly decoded 17; square identified as a missing number on 18. No row-vector arithmetic. |
| 19–20 | nonzero row, leading entry, zero row | Separate selection/meaning decisions precede echelon definition. |
| 21 | echelon form | Defined through established row/entry positions; one violated-condition retrieval. |
| 22–23 | RREF | Defined before contrast; each additional condition has a distinct diagnosis before reuse. |
| 24 | pivot, pivot position, pivot column; pivot/free variables | Names/roles of the same leading-entry structure, with one classification target; operational freedom separately taught 27. |
| 25–26 | consistent, inconsistent, contradiction row | Consistency witness first; opposite case through impossible equality second. |
| 27–29 | arbitrary free choice; unique/infinite cases; echelon consistency criterion | Equality-based worked relation then count contrast and zero-row boundary test; supplied criterion contains only established concepts. |
| 30 | parameter t, parametrization, separate parameter per free variable | Explicit recipe and tuple assembly; varied independent retrieval 34–35 and 38. |
| 31–33 | Gaussian elimination, cancel/skip, back-substitution | Method bridge then analyzed completion and row-swap choice; independent use 36–38. |
| 34–39 | x,y,z and s,t | Reuse of variable, tuple and parameter grammar; no coordinate vectors, span, rank, dimension, linear maps or later-domain examples. |

Rejected examples: line/plane intersections, geometric pivots, row-vector subtraction notation, determinant solving, rank-based free-variable counts, transformations and application-domain models. These add unavailable concepts without helping this chapter’s decisions.

## Repairs and identity review

- Corrected “two or more” linear-system wording to allow one equation; same system-solution target and ID.
- Explicitly established real-number, tuple-equality, array and zero-row grammar; placed solution-set and consistency explanations before reuse.
- Removed row-tuple subtraction from the analyzed solution: it looked like future vector arithmetic; individual entry operations are now used.
- Separated the two RREF defects. The normalization example now has only one failed condition; a new card retrieves the above-pivot defect.
- Corrected pivot terminology: the pivot is an entry, its position a location, and the augmented constant column may have a pivot without representing a variable.
- Taught operational freedom and basic isolation before requesting unique/infinite or parameter reasoning.
- Added actual completion and two-parameter transfer problems; made parametrization one requested result with pivot identification inside the method.
- Removed the supplied contradiction label from the final problem; the learner must inspect the row.
- All 27 old IDs remain attached to their original retrieval decisions; 12 distinct new decisions receive new UUIDs. No aliases existed to preserve.

## Answer review and validation

All 39 answers were reviewed only after their front dependency records were complete. No answer-only vocabulary is used to bypass a required first explanation. A final repair removed premature “linear systems” wording from answer 3; the system concept first appears on front 5. Front 28 now explicitly glosses both unique and infinitely-many solution counts.

- Mathematical verification: exact rational elimination independently checked the systems on 17–18, 29, 32–39; entrywise inverse checks verified the two partial replacements. Symbolic coefficient checks verified the parametrizations on 30, 34, 35 and 38 for every parameter value. Their answers also establish completeness, not just that the listed tuples work.
- All nine problem solutions begin immediately with IDENTIFY and retain ordered IDENTIFY → PLAN → EXECUTE → EVALUATE. Each EXECUTE starts with the requested result. Each EVALUATE uses substitution, an inverse row operation or an impossible equality; none is a bare correctness assertion.
- No A/S body begins with a bare number followed by a period. No unparsed prose is used to establish learner prerequisites. No figures or figure dependencies exist.
- Stable IDs: 27 preserved, 12 new, 0 removed; 21 existing cards revised and 6 unchanged. Chapter order, subject, tags, prerequisites and all 12 declared provides are preserved. Existing runner-owned authoring/curriculum provenance and generation.toml are not fabricated or overwritten; the invoking isolated CLI owns new-run stamping.

### Atomicity triage

The application flagged its five longest basic fronts for human review, not as validation errors. Each was reviewed: 9 teaches one array encoding and asks one separator interpretation; 14 asks one reversing-operation argument; 24 classifies the two sides of one pivot/free distinction; 30 asks one all-solutions representation; 31 asks why the elimination workflow preserves the original solution set. Their bridge vocabulary is intrinsic to the target, and all non-new concepts are already established. Problem 18 requests a multiplier together with the row it produces as one completed operation, not two unrelated grading decisions.

### Validation evidence and isolation exception

- `flashcards deck stabilize . --check`: passed, no missing IDs.
- `flashcards deck validate .`: parsed exactly 39 cards (30 basic, 9 problem, 0 cloze), with zero parser warnings, KaTeX errors, image errors, identity errors, markup errors, cloze lints or frontmatter lints. The command exits 1 solely because its ordinary collection-path resolver looks for the external deck outside this sandbox; see `01-validation-workspace.json`.
- To test the full graph without changing any edge or leaving the workspace, byte-identical target chapter/deck.toml/generation.toml copies were placed under a temporary `validation/mathematics/linear-algebra` directory, beside copies of only the staged external deck.toml files and capability-summary chapters. `flashcards deck validate .flashcards/work/validation/mathematics/linear-algebra` exits 0: all content checks and the explicit graph (one target chapter, two external decks) pass. See `01-validation-staged-closure.json` and `01-validation-inputs.json` for input hashes. The temporary copies are removed before handoff.
- This is not a claim that the direct workspace command resolved its external path. The semantic cold-start pass and staged-closure validation are distinguished from that environment-specific failure. No missing knowledge or new inbound prerequisite was hidden by the mirror.
- `01-content-checks.json` records independent arithmetic, identity and structure checks. No parser or identity implementation changed, so application regression tests are not applicable.
- Full diffs reviewed for chapter scope and stable-target identity; final `git diff --check` passed; added audit artifacts also passed whitespace checks. Protected context, skills, prerequisites, routing override and later chapters are unchanged.

## Planned versus actual inventory — chapter 01

| Inventory | Planned | Actual | Finding |
|---|---:|---:|---|
| Q/A | 30 | 30 | All operational definitions, bridges and discriminations present. |
| P/S | 9 | 9 | All nine planned problem roles present, each with complete IPEE. |
| C | 0 | 0 | Intentionally omitted: no useful standalone exact deletion. |
| Total scheduled cards | 39 | 39 | No unexplained omissions or type substitutions. |
| New / preserved IDs | 12 / 27 | 12 / 27 | No removed cards or transferred mastery. |
| Figures | 0 | 0 | Exact array notation covers the structural targets; every other opportunity has a documented prerequisite or retrieval-role reason for omission. |

Problem reconciliation: analyzed replacement 17; multiplier completion 18; back-substitution completion 32; faded RREF description 34; two-parameter variation 35; independent unique, no-solution and infinite-solution problems 36–38; mixed contradiction priority 39. Figure opportunities and all omitted media are detailed in the design ledger. No figure quota drove the choice.

## Handoff

The first-use frontier and all 39 dependency rows have no unresolved entries. This is an authoring audit, not evidence of learner trial results or a new approval event. Deck status remains pilot-approved, and this run ends at chapter 1 as requested. Local edits only; no commit, push, remote creation or deployment.
