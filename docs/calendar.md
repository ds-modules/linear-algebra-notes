# Shared Calendar (Linear Algebra — Math 279)

**Spine:** Math 279 Canvas Units 1–7 ([canvas/](canvas/)).  
**Enrich from:** Math 56 textbook/projects and EECS 16A applied labs where they complement 279.  
**Coding:** Week 0 bootcamp (tooling only), then LA ops when the math arrives.

| Wk | Math topics | Skills / applications | Canvas / textbook | 56 / 16A reference | Assignments / labs |
|---|---|---|---|---|---|
| 0 | Pre-term coding readiness | Jupyter, Python, NumPy create/index/slice/reshape, elementwise `+`/`*`, simple plots — **not** matmul/`solve`/`inv` yet | — | 16A Python Bootcamp (tooling only) | **279 Lab 0** + Bootcamp |
| 1 | Systems of linear equations; substitution and elimination; matrix form | Translate among equations, augmented matrices, and geometry of lines/planes | Unit 1; 56 §§3.1–3.2 | 16A Notes 0–1 (imaging / tomography hook) | Canvas Unit 1 reading + systems worksheet |
| 2 | Gauss–Jordan; RREF; parametric solutions; consistency | Decide unique / infinite / no solution; start `sympy.rref` and `np.linalg.solve` | Unit 1; 56 §§3.1–3.2 | 16A Lec 3 (Gaussian elimination) | **279 Lab 1** + RREF quiz |
| 3 | Matrix operations, transpose, special matrices; inverse | Compose transforms in code; solve `Ax=b` via inverse when appropriate | Units 2.1–2.2; 56 §§5.1–5.2, 6.1 | — | Canvas 2.1–2.2; **279 Lab 2** (ops / inverse) |
| 4 | Elementary matrices; LU / PLU factorization | Factor once, solve many right-hand sides with `scipy.linalg.lu` | Unit 2.3; 56 §6.2 | — | Canvas 2.3; **279 Lab 2 / Test 1** (LU) |
| 5 | Determinants and their properties | Use det as an independence / invertibility test (`np.linalg.det`) | Units 3.1–3.2; 56 Ch.7 | — | Canvas 3.1–3.2 + determinants quiz |
| 6 | Vectors in Rn; vector spaces; subspaces | pandas CSV + light EDA; data-as-vectors; check space axioms | Units 4.1–4.3; 56 §§1.1–1.3 | — | Canvas 4.1–4.3; **279 Lab 4** (AAPL / axioms) |
| 7 | Span; linear independence; basis and dimension | Build and test bases with RREF; interpret dimension of a feature space | Units 4.4–4.5; 56 §1.4 | — | Canvas 4.4–4.5; **279 Lab 4-2** |
| 8 | Rank; column / row / null spaces; coordinates and change of basis | **Gap fill:** explicit null-space + rank–nullity; Midterm 1 | Units 4.6–4.7; 56 §§4.1–4.2, Ch.8 | — | Canvas 4.6–4.7; null-space add-on; Midterm 1 (Wks 1–7) |
| 9 | Dot product, length, angle; inner product spaces; orthogonal projections | Similarity / correlation; projection formula preview | Units 5.1–5.2; 56 §§1.5, 12.1 | 16A APS Task 1 (cross-correlation) | Canvas 5.1–5.2; **279 Lab 5** (dot) + correlation mini-lab |
| 10 | Orthonormal bases; Gram–Schmidt; QR factorization | **Gap fill:** name and compute QR (279 outcome, thin in labs) | Unit 5.3; 56 §11.1 | — | Canvas 5.3; **279 Lab 5** + QR notebook |
| 11 | Least squares; normal equations; linear regression | Fit models on CSVs; interpret residual as orthogonal to column space | 56 §12.2 (+ Canvas 5.2 projections) | **16A APS Task 6** (GPS / positioning) | **279 Labs 4-3, 5** (housing / insurance); optional APS Task 6 |
| 12 | Linear transformations; kernel and range; matrices for transforms | Map geometry (stretch/rotate); Midterm 2 | Units 6.1–6.3; 56 Ch.2 | 56 projects: Linear Classifiers / Computer Graphics (optional) | Canvas 6.1–6.3; Midterm 2 (Wks 8–11) |
| 13 | Eigenvalues, eigenvectors, eigenspaces; diagonalization | Interpret eigen-directions; PageRank / Markov as apps | Units 7.1–7.2; 56 §§10.1–10.2 | 16A Lec 9 (PageRank); 56 Markov project | Canvas 7.1–7.2; `np.linalg.eig` lab; PageRank mini-lab |
| 14 | Break / catch-up |  |  |  |  |
| 15 | Symmetric matrices; orthogonal diagonalization; SVD; PCA | **Named SVD** then `sklearn.PCA`; classify with nearest-centroid | Units 7.3–7.4; 56 §§13.1–13.3 | **16A VR1** (SVD→PCA; adapt off audio OK) | Canvas 7.3–7.4; **279 Lab 7**; VR1-adapted notebook |
| 16 | Cumulative review | Connect systems → subspaces → projections → eigen → SVD |  |  | **279 Test 2**-style blend + practice final |
| 17 | Final |  |  |  | Cumulative final |

## Notes

- Week **11** is inserted (not a Canvas unit title) because least squares is essential for DS and already appears in 279/56/16A materials.
- Canvas HTML readings: [canvas/README.md](canvas/README.md).
- Still out: 16A circuits / touchscreens; Shazam/DFT as required content.
- Open: recover 279 Labs 3 and 6 when available.
