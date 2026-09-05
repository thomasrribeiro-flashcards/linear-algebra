+++
order = 1
subject = "mathematics"
authoring_model = "gpt-6-astra"
authoring_run_id = "request-34"
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
Q: A **linear equation** can be written as a sum of fixed-number multiples of variables equal to a fixed number. With two variables this is \(ax+by=c\), where \(a,b,c\) are fixed numbers; zero coefficients are allowed. What makes \(2x-3y=7\) fit this form?
A: **Each variable has a fixed coefficient:** \(a=2\), \(b=-3\), and the constant is \(c=7\). The same definition allows any finite number of variables, such as \(x+2y-z=4\).

<!-- card-id: a6bd0e82-c154-42e8-89ba-4190ccd1e4d3 -->
Q: **Real numbers** are the values represented by points anywhere on the number line, not only integers. Allow \(x\) to be any real number. What value solves \(2x=1\), despite not being an integer?
A: **\(x=\tfrac12\).** This is an allowed number-line value, and \(2(\tfrac12)=1\). Unless a restriction is stated, variables may take any real-number values.

<!-- card-id: cf4704d3-0f9f-42c0-b04b-ae3e4c3961de -->
Q: Why is \(xy=6\) not a linear equation in the two variables \(x,y\), whereas \(3x+2y=6\) is?
A: **In \(xy\), one variable multiplies another instead of a fixed number multiplying a variable.** In \(3x+2y\), the coefficients \(3\) and \(2\) are fixed; the equation has the required linear form.

<!-- card-id: 41008c2c-81a2-4c09-935f-1cf00a05e5f7 -->
Q: A **linear system** is one or more linear equations imposed simultaneously on the same variables. When do chosen variable values form a solution of the system?
A: **Exactly when they make every equation true.** Satisfying just one of several required equations is not enough.

<!-- card-id: 46faa379-70c9-4796-9da7-d702f891aa75 -->
Q: An **ordered tuple** lists values inside parentheses, separated by commas, in a stated variable order. In order \(x,y\), write \((x\text{-value},y\text{-value})\); the notation \((x,y)=(a,b)\) means \(x=a\) and \(y=b\). What tuple records \(x=3,y=2\) in order \(x,y\)?
A: **\((3,2)\).** Its positions record \(x\), then \(y\). The same convention extends to three or more variables in their stated order.

<!-- card-id: fa5056f3-1dff-4a2b-8c80-0649c3c34344 -->
Q: For the system \(x+y=5\) and \(2x-y=4\), check the proposed solution tuple \((3,2)\), in variable order \(x,y\). What does substitution into both equations show?
A: **The tuple solves the system.** Both checks succeed: \(3+2=5\) and \(2(3)-2=4\).

<!-- card-id: 1dfd6bea-cade-46f9-9fd0-62259d289aaf -->
Q: The **solution set** is the collection of all solution tuples. For the one-equation system \(x+y=5\), someone reports only \((3,2)\), in order \(x,y\). Give a different solution tuple that shows their list is incomplete.
A: **For example, \((4,1)\)**, since \(4+1=5\). One working tuple need not describe the whole solution set.

<!-- card-id: 43a2b6b5-d513-4ccc-a4ad-abfb9b41b8ac -->
Q: A **matrix** is a rectangular array of numbers enclosed in brackets: horizontal lists are **rows**, vertical lists are **columns**, and each number is an **entry**. An **augmented matrix** stores equations by their coefficients and constants. For example, \(x+2y=5\) becomes \(\left[\begin{array}{cc|c}1&2&5\end{array}\right]\), in column order \(x,y\), then constant. What does the vertical bar separate?
A: **The coefficients \(1,2\) from the right-side constant \(5\).** The row records \(x+2y=5\); the bar marks where the equality separates coefficients from the constant, not an extra variable column.

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
Q: One allowed row operation multiplies every entry in a row by the same **nonzero** number. Why must the multiplier be nonzero to guarantee that the system keeps exactly the same solutions?
A: **Multiplication by a nonzero number can be undone by division by that number.** Multiplication by zero cannot be undone and may discard a requirement: \(x=3\) becomes \(0=0\), which no longer requires \(x=3\).

<!-- card-id: e9410163-68c4-4965-a160-a2240d261ebe -->
Q: **Row replacement** adds a multiple of one entire row to a different row, leaving the source row unchanged. For equations that are both true, adding the same multiple of the source equation to the two sides of the other equation gives another true equality. Why can replacing row 2 by row 2 plus twice row 1 not gain extra solutions either?
A: **Subtracting twice the unchanged row 1 recovers the original row 2.** Thus solutions of the new system satisfy the old one as well; the forward addition and its reverse preserve exactly the simultaneous solutions.

<!-- card-id: 56abea86-58ce-4268-a3bb-d1a830c676db -->
Q: The three solution-preserving row changes are collectively called **elementary row operations**. What are the three operations, including the restriction on multiplication?
A: **Swap two rows; multiply every entry of a row by one nonzero number; or add a multiple of one row to a different row.** Each has a reversing operation.

<!-- card-id: 36bc1d25-12f9-4270-a872-490655481662 -->
Q: Two augmented matrices are **row-equivalent** when a finite sequence of elementary row operations changes one into the other. With the same variable-column order, why do they represent systems with the same solution set?
A: **Every operation preserves exactly the simultaneous solutions.** Applying that fact at each step shows that the whole sequence preserves the solution set.

<!-- card-id: 774fbcbe-967e-4787-aaaf-a6c4ed362895 -->
P: For the augmented matrix below, “row 2 \(\leftarrow\) row 2 \(-2\)(row 1)” means replace row 2 by row 2 minus twice row 1. The first new entry is \(2-2(1)=0\). Complete the operation, including the constant column.

\[
\left[\begin{array}{cc|c}1&1&5\\2&1&8\end{array}\right]
\]
S: **IDENTIFY**

This is one elementary row-replacement step.

**PLAN**

Keep row 1. Subtract twice each row-1 entry from the corresponding row-2 entry, including the constant.

**EXECUTE**

**The result is \(\left[\begin{array}{cc|c}1&1&5\\0&-1&-2\end{array}\right]\).** The remaining new entries are \(1-2(1)=-1\) and \(8-2(5)=-2\).

**EVALUATE**

Undo the step: \(0+2(1)=2\), \(-1+2(1)=1\), and \(-2+2(5)=8\), recovering every original row-2 entry.

<!-- card-id: a92d9ead-a9e9-4dd2-87bb-50af7388f59c -->
P: Complete the missing number in “row 2 \(\leftarrow\) row 2 \(-\,\square\)(row 1)” so the first entry of row 2 becomes zero. Then give the new second row, including its constant.

\[
\left[\begin{array}{cc|c}2&1&4\\6&5&14\end{array}\right]
\]
S: **IDENTIFY**

Choose a row-replacement multiplier to cancel the first entry.

**PLAN**

Solve \(6-2\square=0\), then apply that same multiplier to every entry.

**EXECUTE**

**Use \(3\); the new row is \(\left[\begin{array}{cc|c}0&2&2\end{array}\right]\).** The entries are \(6-3(2)=0\), \(5-3(1)=2\), and \(14-3(4)=2\).

**EVALUATE**

Adding three times row 1 back gives \(6,5,14\), the original second row.

<!-- card-id: a58e7ac9-d677-4fda-9aac-100adc2e008d -->
Q: A **nonzero row** has at least one nonzero entry; its **leading entry** is the leftmost nonzero entry. Locate the leading entry in \(\left[\begin{array}{ccc|c}0&3&-2&5\end{array}\right]\).
A: **The leading entry is \(3\), in the second variable column.** Skip initial zeros, but do not skip any nonzero entry.

<!-- card-id: 9eba409d-2f4a-455b-9966-385eb254e28e -->
Q: A **zero row** contains only zeros, including its constant entry. With variable order \(x,y\), what restriction does \(\left[\begin{array}{cc|c}0&0&0\end{array}\right]\) place on a solution tuple?
A: **None: it says \(0x+0y=0\), or \(0=0\).** Every tuple satisfies that row; any other rows still have to be satisfied.

<!-- card-id: 9aa1a776-94f2-453b-ae03-877e5e453a38 -->
Q: A matrix is in **echelon form** when zero rows are below all nonzero rows, each successive nonzero row's leading entry is farther right, and entries below each leading entry are zero. Which condition fails below?

\[
\left[\begin{array}{cc|c}1&2&3\\0&0&0\\0&1&4\end{array}\right]
\]
A: **The zero-row placement condition fails.** The zero row must be below the nonzero rows; ignoring that misplaced row, the leading entries do move to the right.

<!-- card-id: 07cc2c26-8bda-4586-9339-43c418a45561 -->
Q: **Reduced row echelon form (RREF)** is echelon form with two extra conditions: every leading entry is \(1\), and each leading \(1\) is the only nonzero entry in its column. Why is \(\left[\begin{array}{cc|c}2&0&3\\0&1&4\end{array}\right]\) in echelon form but not RREF?
A: **The first leading entry is \(2\), not \(1\).** The staircase and zero conditions hold, but the leading-one condition does not.

<!-- card-id: 61d9e205-782e-46d1-bda7-d76b3219d3ea -->
Q: Every leading entry below is \(1\). Which remaining RREF condition fails?

\[
\left[\begin{array}{cc|c}1&2&5\\0&1&1\end{array}\right]
\]
A: **The leading \(1\) in column 2 is not that column's only nonzero entry:** a \(2\) sits above it. Leading ones alone do not make an echelon matrix reduced.

<!-- card-id: 1ae77cc1-a2d5-46c5-a39e-cab0e409275f -->
Q: In an echelon matrix, a leading entry is a **pivot**; its location is a **pivot position**, and its column is a **pivot column**. A variable in a pivot column is a **pivot variable**; a variable in a column without a pivot is a **free variable**. For \(\left[\begin{array}{cc|c}1&2&5\end{array}\right]\) in variable order \(x,y\), classify the two variables.
A: **\(x\) is pivot and \(y\) is free.** The constant column does not represent a variable; it can contain a pivot in other echelon matrices, but never represents a free variable.

<!-- card-id: 56d11469-d3ad-4573-a382-6ef4c9cbca7f -->
Q: A system is **consistent** when it has at least one solution. The tuple \((2,1)\), in order \(x,y\), satisfies both \(x+y=3\) and \(2x-y=3\). Why is that enough to establish consistency without finding every solution?
A: **One verified solution meets the requirement “at least one.”** Consistency asserts existence, not that the solution is the only one.

<!-- card-id: f5cfb904-2b69-4e17-a28e-d5c98aeb2c66 -->
Q: A system is **inconsistent** when it has no solution. A **contradiction row** represents an impossible equality. With variable order \(x,y\), why does a row \(\left[\begin{array}{cc|c}0&0&1\end{array}\right]\) prove inconsistency?
A: **It requires \(0x+0y=1\), or \(0=1\).** No values can satisfy that row, so no tuple can satisfy every equation.

<!-- card-id: 55d2ab92-bdb5-4b55-a466-14e41cd4ec83 -->
Q: In a consistent RREF system, free variables may be chosen arbitrarily; the equations then determine the pivot variables. For \(x+y=5\), \(y\) is free: subtracting \(y\) from both sides gives \(x=5-y\). If \(y\) changes from \(1\) to \(2\), how must \(x\) change to keep a solution?
A: **\(x\) changes from \(4\) to \(3\).** Each chosen \(y\) gives one corresponding \(x\); a free variable need not be absent from the equations.

<!-- card-id: 94630305-24b2-4691-972d-228f465f27c7 -->
Q: For a consistent linear system over the real numbers, how do free variables distinguish a **unique** solution (exactly one) from **infinitely many** solutions (more than any fixed whole-number count)?
A: **No free variables means a unique solution; at least one free variable means infinitely many.** With no free choice the pivot equations determine every value; otherwise arbitrary real choices give distinct solution tuples.

<!-- card-id: 3001b75a-b798-421a-8d4a-ea6e1bfafa4e -->
Q: An echelon augmented matrix with no contradiction row represents a consistent system. For the matrix below, in variable order \(x,y\), why does the zero row not imply infinitely many solutions?

\[
\left[\begin{array}{cc|c}1&0&2\\0&1&3\\0&0&0\end{array}\right]
\]
A: **Both variable columns have pivots, so there is no free variable and the only solution is \((2,3)\).** The zero row adds no restriction; count free variable columns, not zero rows.

<!-- card-id: 5d387a4c-7fa9-440e-8581-d8513558f8b7 -->
Q: A **parameter** is a symbol allowed to take arbitrary real values. A **parametrization** writes every solution tuple using a separately chosen parameter for each free variable. For \(x+2y=5\), set \(y=t\); subtracting \(2t\) gives \(x=5-2t\). What tuple describes all solutions in order \(x,y\), with what allowed values of \(t\)?
A: **\((x,y)=(5-2t,t)\), for every real \(t\).** Every choice satisfies the equation, and every solution is included by taking \(t\) equal to its \(y\)-value.

<!-- card-id: 624e45a6-404b-410c-9225-ee9dd65bd2f5 -->
Q: **Gaussian elimination** uses elementary row operations to reach echelon form: work left to right, swap in a nonzero entry when needed, and cancel entries below it. Skip a column if every remaining entry in it is zero. For a consistent result, assign any free variables and solve upward from the last nonzero row (**back-substitution**). Why does this solve the original system?
A: **All intermediate augmented matrices are row-equivalent to the original, so their solution sets agree.** A contradiction row instead means no solution; continuing to RREF by making pivots \(1\) and clearing above them is another way to read the same solution set.

<!-- card-id: 7a53ead1-5493-4a1d-99b2-976088bce643 -->
P: Use back-substitution to finish solving the echelon system \(x+y=7\), \(2y=4\). The last equation gives \(y=2\) after division by \(2\). Complete the solution tuple in order \(x,y\).
S: **IDENTIFY**

The last variable is known; back-substitution determines the remaining one.

**PLAN**

Put \(y=2\) into \(x+y=7\), then subtract \(2\).

**EXECUTE**

**The solution is \((x,y)=(5,2)\).** From \(x+2=7\), obtain \(x=5\).

**EVALUATE**

Both original equations hold: \(5+2=7\) and \(2(2)=4\).

<!-- card-id: 00aca5e5-442a-4c86-8314-b761e96311ca -->
Q: To begin Gaussian elimination in the first variable column of \(\left[\begin{array}{cc|c}0&1&2\\2&1&6\end{array}\right]\), which elementary row operation supplies a nonzero leading entry in the top row without dividing by zero?
A: **Swap rows 1 and 2.** The top row then begins with \(2\); the zero at the original top-left position did not mean the whole column was unusable.

<!-- card-id: c57c2f83-581f-4259-b3c4-f42d43bb2e76 -->
P: The matrix below is in RREF, with variable columns ordered \(x,y,z\). Give a parametric tuple describing every solution.

\[
\left[\begin{array}{ccc|c}1&0&2&4\\0&1&-1&3\end{array}\right]
\]
S: **IDENTIFY**

The system is consistent, with \(x,y\) pivot variables and \(z\) free.

**PLAN**

Set \(z=t\) and solve the two pivot equations for \(x,y\).

**EXECUTE**

**The solutions are \((x,y,z)=(4-2t,3+t,t)\) for every real \(t\).** The equations \(x+2z=4\) and \(y-z=3\) give \(x=4-2t\) and \(y=3+t\).

**EVALUATE**

Substitution gives \((4-2t)+2t=4\) and \((3+t)-t=3\). Conversely, any solution must have \(t=z\) and these same \(x,y\), so none are omitted.

<!-- card-id: e85b3451-394b-4daa-98c9-dc9818b29578 -->
P: For the one-row RREF system \(\left[\begin{array}{ccc|c}1&2&-1&4\end{array}\right]\), with variable order \(x,y,z\), give all solution tuples using a separate parameter for each free variable.
S: **IDENTIFY**

The system is consistent; \(x\) is pivot, while \(y,z\) are free.

**PLAN**

Choose \(y=s\) and \(z=t\) separately, then isolate \(x\).

**EXECUTE**

**Every solution is \((x,y,z)=(4-2s+t,s,t)\), with \(s\) and \(t\) arbitrary real numbers chosen separately.** The row says \(x+2y-z=4\).

**EVALUATE**

Substitution gives \((4-2s+t)+2s-t=4\). Every solution is captured by \(s=y,t=z\); forcing \(s=t\) would miss solutions whose \(y,z\) differ.

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

Use elimination to determine whether the second equation adds a requirement.

**PLAN**

Replace row 2 by row 2 minus twice row 1, then parametrize any free variable.

**EXECUTE**

**Every solution is \((x,y)=(4-2t,t)\), for any real \(t\).** Elimination gives \(\left[\begin{array}{cc|c}1&2&4\\0&0&0\end{array}\right]\). Thus \(y=t\) is free and \(x=4-2t\).

**EVALUATE**

Substitution gives \((4-2t)+2t=4\) and twice this equality gives the second equation. Conversely, each solution has some \(y=t\), which forces the stated \(x\).

<!-- card-id: fa06f1b1-8509-408f-8ebb-b80210f0696d -->
P: The matrix below is in RREF, with variable columns ordered \(x,y,z\). Does its system have no solution or infinitely many solutions? Identify the feature that decides, even though some variable columns have no pivot.

\[
\left[\begin{array}{ccc|c}1&0&2&0\\0&0&0&1\end{array}\right]
\]
S: **IDENTIFY**

Classify the system before assigning arbitrary values to nonpivot variables.

**PLAN**

Check for a contradiction before using free variables to distinguish consistent cases.

**EXECUTE**

**The system has no solution.** The last row requires \(0=1\); the pivot in the constant column signals inconsistency.

**EVALUATE**

Every possible tuple still leaves that last equation as \(0=1\). Nonpivot variable columns cannot repair it.
