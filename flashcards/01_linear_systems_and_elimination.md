+++
order = 1
subject = "mathematics"
authoring_model = "gpt-5.6-sol"
authoring_run_id = "request-26"
authoring_provider = "openai"
authoring_reasoning_effort = "high"
curriculum_model = "gpt-5.6-sol"
curriculum_run_id = "request-25"
curriculum_provider = "openai"
curriculum_reasoning_effort = "high"
tags = ["linear-algebra", "linear-systems", "gaussian-elimination"]
prerequisites = []
provides = [
  "simultaneous-linear-equations",
  "linear-system",
  "linear-system-solution-tuple",
  "augmented-matrix",
  "elementary-row-operation",
  "row-equivalence",
  "echelon-form",
  "reduced-row-echelon-form",
  "pivot-and-free-variable",
  "linear-system-consistency",
  "linear-system-parametrization",
  "gaussian-elimination",
]
+++

# Linear systems and elimination

<!-- card-id: aafa6b16-5328-459a-bdaf-1dd5bc51d152 -->
Q: The equations \(x+y=5\) and \(x-y=1\) are required at the same time. What must chosen values of \(x\) and \(y\) do to meet this simultaneous requirement?
A: **They must make both equations true.** For example, \(x=3\) and \(y=2\) work because \(3+2=5\) and \(3-2=1\).

<!-- card-id: c4bd6239-b161-43f9-b605-f68c83c5fbb0 -->
Q: In this chapter, a **linear equation in \(x\) and \(y\)** can be written \(ax+by=c\), where \(a\), \(b\), and \(c\) are fixed numbers. Does \(2x-3y=7\) have this form? Give the decisive reason.
A: **Yes.** Each variable is multiplied by a fixed number, the resulting terms are added, and their sum equals a fixed number.

<!-- card-id: 41008c2c-81a2-4c09-935f-1cf00a05e5f7 -->
Q: A **linear system** is two or more linear equations imposed simultaneously. When do chosen variable values form a solution of the system?
A: **They form a solution exactly when they make every equation in the system true.** Satisfying only one equation is not enough.

<!-- card-id: 46faa379-70c9-4796-9da7-d702f891aa75 -->
Q: An **ordered tuple** records variable values in a fixed order. If the stated order is \(x\), then \(y\), what tuple records \(x=3\) and \(y=2\)?
A: **\((3,2)\).** The first position records \(x\); the second records \(y\).

<!-- card-id: fa5056f3-1dff-4a2b-8c80-0649c3c34344 -->
Q: Is \((3,2)\) a solution tuple of the system \(x+y=5\) and \(2x-y=4\)? Justify the decision by substitution.
A: **Yes.** Substitution gives \(3+2=5\) and \(2(3)-2=4\), so both equations are true.

<!-- card-id: 43a2b6b5-d513-4ccc-a4ad-abfb9b41b8ac -->
Q: The **augmented matrix** below stores one equation per horizontal row. Its vertical columns contain the coefficients of \(x\), the coefficients of \(y\), and the right-side constants, in that order; each stored number is an **entry**. What does the vertical bar separate?

\[
\left[\begin{array}{cc|c}
1 & 2 & 5\\
3 & -1 & 4
\end{array}\right]
\]
A: **It separates the variable coefficients from the right-side constants.** Brackets mark the whole array; the entries to the right of the bar form the augmented constant column.

<!-- card-id: a1715ef3-92e4-4070-b50c-7b5a25338280 -->
Q: Write the augmented matrix for the system \(x+2y=5\) and \(3x-y=4\), keeping the columns in the order \(x,y\), then constants.
A: **The augmented matrix is**

\[
\left[\begin{array}{cc|c}
1 & 2 & 5\\
3 & -1 & 4
\end{array}\right].
\]

Each row copies the coefficients and constant from its equation.

<!-- card-id: d94d40ec-df51-40e3-8391-a317e75ff68a -->
Q: The variable columns of the augmented matrix below are ordered \(x,y\). Which system of equations does it represent?

\[
\left[\begin{array}{cc|c}
2 & -1 & 7\\
0 & 3 & 6
\end{array}\right]
\]
A: **It represents \(2x-y=7\) and \(3y=6\).** A zero coefficient means the second equation has no \(x\)-term.

<!-- card-id: 030f55d1-4652-4e87-9876-2023913255b6 -->
Q: Swapping two rows of an augmented matrix merely exchanges the order of two equations. Why does this operation preserve the system's solution tuples?
A: **The simultaneous requirements are unchanged.** Their order does not affect which values make every equation true, and swapping the rows again reverses the operation.

<!-- card-id: cdea1488-87fa-488b-b194-bcc35c7ef19d -->
Q: One allowed row operation multiplies every entry in a row by the same **nonzero** number. Why must the number be nonzero if all solution tuples are to be preserved?
A: **A nonzero multiplication is reversible by division by that number.** Multiplying by zero would erase the equation's information and cannot be reversed.

<!-- card-id: e9410163-68c4-4965-a160-a2240d261ebe -->
Q: Another allowed row operation replaces one row by that row plus a multiple of a different row. Why does this preserve all solution tuples?
A: **The operation is reversible.** Subtracting the same multiple of the unchanged row recovers the original row, so no simultaneous solution is gained or lost.

<!-- card-id: 56abea86-58ce-4268-a3bb-d1a830c676db -->
Q: What are the three **elementary row operations** that preserve all solution tuples of a system represented by an augmented matrix?
A: **Swap two rows; multiply a row by a nonzero number; or add a multiple of one row to a different row.** Each operation is reversible.

<!-- card-id: 36bc1d25-12f9-4270-a872-490655481662 -->
Q: The **solution set** is the collection of all solution tuples. Two augmented matrices are **row-equivalent** when a finite sequence of elementary row operations changes one into the other. Why do row-equivalent augmented matrices represent systems with the same solution set?
A: **Every step is reversible and preserves all simultaneous solutions.** Therefore the complete sequence preserves the solution set in both directions.

<!-- card-id: 774fbcbe-967e-4787-aaaf-a6c4ed362895 -->
P: For the augmented matrix below, the notation “row 2 \(\leftarrow\) row 2 \(-2\)(row 1)” means to replace row 2 by row 2 minus twice row 1. Carry out this operation so the first entry of row 2 becomes zero.

\[
\left[\begin{array}{cc|c}
1 & 1 & 5\\
2 & 1 & 8
\end{array}\right]
\]
S: **IDENTIFY**

This is one elementary row-replacement step on an augmented matrix.

**PLAN**

Keep row 1 unchanged. Subtract twice each entry of row 1 from the corresponding entry of row 2.

**EXECUTE**

**The result is \(\left[\begin{array}{cc|c}1&1&5\\0&-1&-2\end{array}\right]\).** The new second row is \((2,1,8)-2(1,1,5)=(0,-1,-2)\).

**EVALUATE**

Adding twice row 1 back to the new row 2 gives \((2,1,8)\), recovering the original row and checking reversibility.

<!-- card-id: a58e7ac9-d677-4fda-9aac-100adc2e008d -->
Q: The **leading entry** of a nonzero row is its leftmost nonzero entry. What is the leading entry of \(\left[\begin{array}{ccc|c}0&3&-2&5\end{array}\right]\), and where is it located?
A: **The leading entry is \(3\), in the second variable column.** The initial zero is skipped when locating the leftmost nonzero entry.

<!-- card-id: 9aa1a776-94f2-453b-ae03-877e5e453a38 -->
Q: A row containing only zeros is a **zero row**. A matrix is in **echelon form** when all zero rows are at the bottom, each lower leading entry lies to the right of the one above it, and every entry below a leading entry is zero. Which condition fails below?

\[
\left[\begin{array}{cc|c}
1&2&3\\
0&0&0\\
0&1&4
\end{array}\right]
\]
A: **The zero-row placement condition fails.** A zero row appears above a nonzero row, so the matrix is not in echelon form.

<!-- card-id: 07cc2c26-8bda-4586-9339-43c418a45561 -->
Q: **Reduced row echelon form (RREF)** adds two conditions to echelon form: every leading entry equals \(1\), and each leading \(1\) is the only nonzero entry in its column. Why is \(\left[\begin{array}{cc|c}2&1&3\\0&1&4\end{array}\right]\) in echelon form but not in RREF?
A: **Its first leading entry is \(2\), not \(1\).** It satisfies the staircase and below-leading-entry conditions, but it fails an added RREF condition.

<!-- card-id: 1ae77cc1-a2d5-46c5-a39e-cab0e409275f -->
Q: In an echelon augmented matrix, a leading entry in a variable column is a **pivot position**. Its variable is a **pivot variable**; a variable whose column has no pivot is a **free variable**. In \(\left[\begin{array}{cc|c}1&2&5\end{array}\right]\), which variable is pivot and which is free when the columns are \(x,y\)?
A: **\(x\) is the pivot variable and \(y\) is free.** The \(x\)-column contains the leading entry, while the \(y\)-column has no pivot.

<!-- card-id: f5cfb904-2b69-4e17-a28e-d5c98aeb2c66 -->
Q: A system is **consistent** if it has at least one solution and **inconsistent** if it has none. A row that represents an impossible equality such as \(0=1\) is a **contradiction row**. Why does \(\left[\begin{array}{cc|c}0&0&1\end{array}\right]\) prove inconsistency?
A: **It represents the impossible equation \(0=1\).** No variable values can make that contradiction true, so the whole simultaneous system has no solution.

<!-- card-id: 94630305-24b2-4691-972d-228f465f27c7 -->
Q: In this chapter, variables may take values represented on the usual number line; these are called **real numbers**. Assume an echelon form shows that a system is consistent. How do free variables distinguish a unique solution from infinitely many solutions?
A: **No free variables means one unique solution; at least one free variable means infinitely many solutions.** A free variable can be assigned any real-number value, producing different solution tuples.

<!-- card-id: 5d387a4c-7fa9-440e-8581-d8513558f8b7 -->
Q: A **parameter** is a new symbol used to range over all choices for a free variable. For \(x+2y=5\), let the free variable be \(y=t\). What parametric tuple describes every solution in the order \(x,y\)?
A: **\((x,y)=(5-2t,t)\) for every real number \(t\).** Choosing \(t\) fixes \(y\), and the equation then fixes \(x\).

<!-- card-id: 624e45a6-404b-410c-9225-ee9dd65bd2f5 -->
Q: **Gaussian elimination** uses elementary row operations to reach echelon form, then solves from the last nonzero row upward by substitution into earlier rows. Why does this workflow solve the original system rather than only the final one?
A: **Every intermediate augmented matrix is row-equivalent to the original and has the same solution set.** Solving upward is often called back-substitution; continuing the row operations to RREF instead makes the pivot equations directly readable.

<!-- card-id: c57c2f83-581f-4259-b3c4-f42d43bb2e76 -->
P: The matrix below is in RREF, with variable columns ordered \(x,y,z\). Identify the pivot and free variables, then give a parametric tuple for every solution.

\[
\left[\begin{array}{ccc|c}
1&0&2&4\\
0&1&-1&3
\end{array}\right]
\]
S: **IDENTIFY**

This is a consistent RREF system whose variable columns must be classified by their pivots.

**PLAN**

Find the leading \(1\)s, choose a parameter for each nonpivot variable, and solve the pivot equations.

**EXECUTE**

**The solutions are \((x,y,z)=(4-2t,3+t,t)\) for every real number \(t\).** The pivot variables are \(x\) and \(y\); \(z\) is free, so set \(z=t\). Then \(x+2z=4\) gives \(x=4-2t\), and \(y-z=3\) gives \(y=3+t\).

**EVALUATE**

Substitution gives \((4-2t)+2t=4\) and \((3+t)-t=3\), so every stated tuple satisfies both rows.

<!-- card-id: 41e066d3-fc37-4243-a32f-620ed132dfe2 -->
P: Solve the system \(x+y=5\) and \(2x-y=1\) by Gaussian elimination. Give the solution tuple in the order \(x,y\).
S: **IDENTIFY**

This is a two-variable linear system suited to elimination.

**PLAN**

Write the augmented matrix, replace row 2 by row 2 minus twice row 1, then back-substitute.

**EXECUTE**

**The solution is \((x,y)=(2,3)\).** Starting from \(\left[\begin{array}{cc|c}1&1&5\\2&-1&1\end{array}\right]\), row 2 \(\leftarrow\) row 2 \(-2\)(row 1) gives \(\left[\begin{array}{cc|c}1&1&5\\0&-3&-9\end{array}\right]\). Thus \(y=3\), and \(x+y=5\) gives \(x=2\).

**EVALUATE**

Substitution into the original equations gives \(2+3=5\) and \(2(2)-3=1\).

<!-- card-id: 678357f5-ffbb-4fe0-b8f1-f225553d0322 -->
P: Classify the system \(x+y=2\) and \(2x+2y=5\) as having no solution, one solution, or infinitely many solutions. Use elimination to justify the classification.
S: **IDENTIFY**

This is a solution-case classification for a two-variable linear system.

**PLAN**

Eliminate \(x\) from the second equation and inspect the resulting row for a contradiction, pivots, or a free variable.

**EXECUTE**

**The system has no solution.** Row 2 \(\leftarrow\) row 2 \(-2\)(row 1) changes the augmented matrix to \(\left[\begin{array}{cc|c}1&1&2\\0&0&1\end{array}\right]\), whose second row says \(0=1\).

**EVALUATE**

The first equation would imply \(2x+2y=4\) after multiplication by \(2\), which cannot equal the required \(5\).

<!-- card-id: 695ed977-e266-4f3b-85da-0fb96e40af16 -->
P: Solve and parametrize the system \(x+2y=4\) and \(2x+4y=8\). Give every solution tuple in the order \(x,y\).
S: **IDENTIFY**

This is a consistent system that may have a free variable after elimination.

**PLAN**

Eliminate \(x\) from the second row, classify the remaining variables, and assign a parameter to any free variable.

**EXECUTE**

**Every solution is \((x,y)=(4-2t,t)\) for a real number \(t\).** Row 2 \(\leftarrow\) row 2 \(-2\)(row 1) produces a zero row. The remaining equation is \(x+2y=4\); \(y\) is free, so set \(y=t\) and obtain \(x=4-2t\).

**EVALUATE**

Substitution gives \((4-2t)+2t=4\); doubling this equality also gives the second original equation.

<!-- card-id: fa06f1b1-8509-408f-8ebb-b80210f0696d -->
P: The RREF matrix below has a free variable column and a contradiction row. Does its system have no solution or infinitely many solutions? State which feature decides.

\[
\left[\begin{array}{ccc|c}
1&0&2&0\\
0&0&0&1
\end{array}\right]
\]
S: **IDENTIFY**

This is a mixed classification in which two familiar visual cues point toward different cases.

**PLAN**

Check consistency before using the number of free variables to classify a consistent system.

**EXECUTE**

**The system has no solution.** The last row represents \(0=1\), so the system is inconsistent; the free variable cannot create a solution to an impossible equation.

**EVALUATE**

Any proposed variable values leave the last row unchanged as \(0=1\), confirming that no tuple can satisfy every row.
