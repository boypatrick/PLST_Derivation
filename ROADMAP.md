# PLST Derivation Roadmap

Last updated: 2026-05-01

## Positioning

The paper should be framed as a conditional action-level theorem for the
three-generation multiplicity of the SM chiral family representation under the
PSLT two-center projection data.  It should not claim to derive the full
Standard Model, the SM gauge group, the two-center divisor, or the exclusivity
condition from nothing.

Recommended abstract/conclusion wording:

```text
a first-principles projection-spectral derivation of the three-generation
multiplicity of the SM chiral family representation, conditional on the PSLT
two-center projection data.
```

## Accepted Core Theorem

The current core theorem is mathematically sound under its stated assumptions:

```text
C = CP^1,
R = p_+ + p_-,
L_R = O(R) = O(2),
D_R = sqrt(2)(dbar_{L_R} + dbar_{L_R}^\dagger),
Ker D_R^+ ~= H^0(C,L_R),
Ker D_R^- ~= H^1(C,L_R),
h^0(CP^1,O(2)) = 3,
h^1(CP^1,O(2)) = 0.
```

Therefore, if all other SM-charged sectors are absent from the kernel or fully
paired and gapped, `N_gen = 3` and there are no unpaired light SM-charged
exotics.

## Revision Tasks

### R1. Add Product Dirac Action and 4D Weyl Reduction

Priority: highest.
Status: completed.

Add the explicit product-space fermion action after the parent action:

```text
X = M_4 x C,
D_X = Dslash_{M_4} tensor 1 + gamma_5 tensor D_R,
S_fermion^gen = int_{M_4 x C} dvol_{M_4} dvol_C \bar Psi i D_X Psi.
```

Also add mode expansion:

```text
Psi(x,y) =
  sum_alpha psi_alpha^+(x) u_alpha^+(y)
  + sum_beta psi_beta^-(x) u_beta^-(y)
  + massive internal modes,

D_R u_alpha^+ = 0,   u_alpha^+ in Ker D_R^+,
D_R u_beta^- = 0,    u_beta^- in Ker D_R^-.
```

State the product chirality convention:

```text
Gamma_X = gamma_5 tensor Gamma_C.
```

Goal: make the chain explicit:

```text
internal Spin^c zero mode -> massless 4D Weyl fermion -> SM chiral generation.
```

### R2. Strengthen the Exclusivity Condition

Priority: highest.
Status: completed.

Replace or supplement `ind D_vec = 0`.  Index zero excludes extra net chirality,
but does not exclude massless vectorlike SM-charged exotics.

Use one of:

```text
Ker D_vec = 0,
```

or

```text
dim Ker D_vec^+ = dim Ker D_vec^-,
```

with a full-rank gauge-invariant mass pairing

```text
M_vec: Ker D_vec^+ -> Ker D_vec^-.
```

Separate the two claims:

- no fourth chiral SM generation follows from the nonzero-index carrier;
- no extra light SM-charged exotics additionally requires a gap/full-rank
  vectorlike pairing.

### R3. Clarify Spin^c Determinant-Line Conventions

Priority: high.
Status: completed.

Add a sentence in the Spin^c section:

```text
We use the canonical Spin^c structure on the complex curve C, whose spinor
bundle is Lambda^{0,*}T^*C.  The line bundle L_R is an auxiliary twisting
bundle for the Dolbeault-Dirac operator, not the Spin^c determinant line itself.
```

This prevents confusion between the Dolbeault index
`chi(C,L_R)` and determinant-line conventions.

### R4. Make S_proj a Cohomological Constraint

Priority: high.
Status: completed.
Resolution: `S_proj` is now formulated first as the cohomological condition
`[i F_{A_R}/(2 pi)] = PD(R) = [p_+] + [p_-]`.  The action-like expression is
kept only as a regulated current implementation using a smooth representative
`J_R^(epsilon)`.

Avoid reading the current `S_proj` as a pointwise smooth curvature equation.
State the robust condition:

```text
[ i F_{A_R} / (2 pi) ] = [p_+] + [p_-] in H^2(C,Z),
c_1(L_R) = PD(R),   R = p_+ + p_-.
```

If the action-like current expression remains, state that it is a topological
constraint or a regulated limit of smooth representatives of the Poincare dual
currents.

### R5. Fix the Canonical Basis Normalization

Priority: high.
Status: completed.
Resolution: the residual scale in `zeta_R -> a zeta_R` is fixed by the physical
projection map `pi_D`; the midplane condition `z_ax = 0 => |zeta_R| = 1` fixes
the real scale, and the axial-angle origin fixes the residual phase.

The coordinate choice placing `p_+ -> 0` and `p_- -> infinity` leaves a residual
scale freedom `zeta_R -> a zeta_R`.  This changes the moment map unless the scale
is fixed.

Choose one route:

1. Define `zeta_R` by the physical projection map `pi_D`, including its scale.
2. Define `mu_R` intrinsically by a Green/moment equation:

```text
Delta_C mu_R = const*(delta_{p_+} - delta_{p_-}),
int_C mu_R omega_FS = 0,
normalization fixed.
```

Then `T_R = P_R M_{mu_R} P_R` is genuinely canonical.

### R6. Define the Projection Map pi_D and the Parameter eta

Priority: high.
Status: completed.
Resolution: `pi_D` is defined by
`zeta_R = sqrt(r_+/r_-) exp(i phi)` and maps the regulated two-center spatial
chart to `CP^1`, with `x_+ -> p_+` and `x_- -> p_-` in the collapsed-core limit.
The parameter `eta(D,epsilon)` is defined as the source-overlap integral
`int d^3x sqrt(rho_epsilon(x-x_+) rho_epsilon(x-x_-))` and enters `K_N`,
`A_{N,pm}`, and `chi_N`.

Add a subsection defining

```text
pi_D: R^3 -> C,
pi_D(x_+) = p_+,
pi_D(x_-) = p_-.
```

State how it depends on `(rho, z_ax, phi; D, epsilon)` and whether axial
symmetry removes `phi`.

Define `eta`, or remove it.  If retained:

```text
eta denotes the center-overlap / kinetic-mixing control parameter and enters
K_N(D,eta), A_{N,pm}(D,eta), and chi_N(D,eta).
```

### R7. Treat S_Omega as a Static Functional

Priority: medium.
Status: completed.
Resolution: the parent action now uses `S_Omega^cov`, while the displayed
three-dimensional two-center variational object is renamed `E_Omega` and
explicitly described as the static-sector reduction.

The current `S_Omega` is a three-dimensional static variational functional, not
a four-dimensional Lorentz-covariant action.  Either:

- rename it `E_Omega`, or
- state that in the static two-center sector the covariant parent reduces to
  the displayed spatial functional.

### R8. Mark Formation Law as Effective Kinetics

Priority: medium.
Status: completed.
Resolution: the probability module is now explicitly framed as a
coarse-grained effective formation/visibility model.  The Schur complement has
the gap assumption `0 notin Spec(Q_N^cc K_N Q_N^cc)`, with reduced
resolvent/pseudoinverse noted as the fallback.  The WKB barrier region
`B_{N,pm}` and positive-part integrand are defined.

In the abstract and body, prefer:

```text
the two-center geometry supplies scalar spectral data used in an effective
formation/visibility model.
```

Add assumptions for the Schur complement:

```text
0 notin Spec(Q_N^cc K_N Q_N^cc),
```

or replace the inverse by a reduced resolvent/pseudoinverse.

Define the WKB barrier region:

```text
B_pm = {s : V_eff(s) > omega_N^2},
S_WKB = int ds sqrt((V_eff - omega_N^2)_+).
```

### R9. Add Standard One-Family Checks

Priority: medium.
Status: completed.
Resolution: the paper now states the global group
`G_SM = (SU(3) x SU(2) x U(1))/Z_6`, clarifies that local anomaly equations fix
hypercharge only up to normalization, and adds both the `SU(3)^3` and Witten
`SU(2)` anomaly checks.

Add:

```text
SU(3)^3: 2 A(3) - A(bar 3) - A(bar 3) = 0.
```

Add Witten SU(2) global anomaly check:

```text
3 color copies of Q + 1 lepton doublet = 4 SU(2) Weyl doublets per family,
which is even.
```

Clarify hypercharge normalization.  Either work at Lie-algebra level or state
the global group as

```text
G_SM = (SU(3) x SU(2) x U(1)) / Z_6.
```

### R10. Notation Hygiene

Priority: low.
Status: completed.
Resolution: the paper now has a notation-conventions subsection.  `D` is
reserved for two-center separation, Dirac-type operators use `mathscr D`,
`P_R`, `P_N^cc`, `Pi_N`, and `P_N(t;D,eta)` are explicitly separated, and the
protected degeneracy is written as `g_N^{chiral}` in the zero-mode and
probability formulas.

- Keep `D` for center separation and `mathscr D_R` for Dirac operators.
- Keep `P_R` for Bergman projection, `P_N^cc` for collective-coordinate
  projection, and `P_N(t)` for probabilities.
- Use `g_N^{chiral}` when discussing protected zero-mode degeneracy.

## Post-R10 Review Tasks

The latest review confirms that the Spin^c zero-mode theorem and product Dirac
reduction are now structurally sound.  Several comments in that review refer to
items already closed in R4-R10 (`pi_D`, `eta`, `S_proj`, `E_Omega`, Schur gap,
WKB barrier, anomaly checks, and notation hygiene).  Do not reopen those unless
a new, concrete mathematical error is found.

### R11. Define the Generation-to-Spatial Mode Assignment

Priority: high.
Status: completed.
Resolution: Section IX now separates the generation Hilbert space
`H_gen=H^0(C,L_R)` from the scalar spatial Hilbert space `H_Omega(D)`,
defines the raw scalarization operator/profile map interface, introduces
spectral weights `mu_{nN}=|<psi_n,c_D(u_N)>|^2`, and treats the hard map
`I_D(u_N)=psi_{n(N;D)}` only as the isolated-maximum/gap limit.

The remaining real interface gap is the relation between:

```text
u_N in H^0(C,L_R)
```

and scalar spatial eigenmodes

```text
[-nabla^2 + V_eff] psi_n = omega_n^2 psi_n.
```

Add a dedicated subsection before the kinetic definitions:

```text
Generation-to-spatial mode assignment.
```

Define either a mode-locking map

```text
I_D: H^0(C,L_R) -> H_Omega^scalar
```

or an assignment

```text
N -> n(N;D),
u_N -> psi_{n(N)}(.;D),
omega_N := omega_{n(N)}.
```

State explicitly:

- the Spin^c theorem fixes the three protected generation modes `u_N`;
- the scalar sector supplies only formation and visibility data;
- `Gamma_N`, `omega_N`, and `|N,pm>` use scalar data only after this
  mode-locking prescription;
- `u_N` and `psi_n` are not the same object.

### R12. Upgrade Visibility to a Bundle-Valued Pairing

Priority: medium.
Status: completed.
Resolution: Section IX now treats `u_hat_N` as a pullback section
`pi_D^*u_N in Gamma(R^3, pi_D^*L_R)`, introduces the pullback Hermitian
metric `h_hat_R`, and writes `y_N^eff` as the invariant pairing
`int <u_hat_N,J_vis>_{h_hat_R} dmu_cyl`.  The older
`overline{u_hat_N} f_L f_R W_frame` expression is retained only as a local
trivialized representative.  A frame-change check now shows explicitly that
`H_R overline{U_N} J_vis` is invariant under `e_hat_R -> g e_hat_R`.

The current visibility integral is acceptable in a local trivialization, but it
should be made geometrically invariant.  Since `u_N` is a section of `L_R`, its
pullback satisfies

```text
u_hat_N in Gamma(pi_D^* L_R).
```

Rewrite the visible overlap as a Hermitian pairing on the pullback bundle:

```text
y_N^eff =
  y_0 int_{R^3} <u_hat_N, J_vis>_{pi_D^* L_R} dmu_cyl.
```

Then state that the local formula with

```text
overline{u_hat_N} f_L f_R W_frame
```

is a trivialized representative where `W_frame` contains the bundle frame,
Hermitian metric, Jacobian, angular-channel projection, and any remaining
complex conjugation convention.

### R13. Refine Hard Locking into Spectral Scalarization and Soft Assignment

Priority: high.
Status: completed.
Resolution: The hard locking map is now derived only after defining the raw
scalarization operator/profile map interface, the scalar spectral weights
`mu_{nN}`, and the gap condition
`mu_{n(N),N} - sup_{m != n(N)} mu_{mN} >= Delta_lock`.  If the gap condition
fails, the paper uses a soft assignment
`Gamma_N^soft=sum_n mu_{nN} Gamma_n`, or the corresponding spectral-measure
integral for continuous spectrum.

Acceptance criteria:

- `u_N`, `u_hat_N`, and `psi_n` live in explicitly distinct spaces.
- The interface from generation zero modes to scalar profiles is explicit, not
  a silent identification of bases.
- `I_D` and `psi_N^lock` appear only after an isolated maximum/gap condition.
- The probability law states how to replace `Gamma_N` by `Gamma_N^soft` when
  hard locking fails.

### R14. Abstract and Notation Consistency

Priority: high.
Status: completed.
Resolution: The abstract now uses scalar spectral labels `psi_n, omega_n`
instead of an unqualified `psi_N, omega_N`, defines `Gamma_N^eff` in the
probability law, and states that hard-locking is required before introducing
`psi_N^lock`, `omega_N`, and `Gamma_N`; otherwise `Gamma_N^eff=Gamma_N^soft`.

Acceptance criteria:

- The abstract does not use `psi_N` for an unlocked scalar eigenmode.
- The abstract probability law uses `Gamma_N^eff`.
- The hard/soft distinction is stated before the abstract interprets the
  formation/visibility weights.

### R15. Linear Scalarization Map

Priority: high/medium.
Status: completed.
Resolution: Section IX now separates the linear raw scalarization operator
`Ctilde_D u = w_D^{1/2}<j_D,pi_D^*u>_{h_hat_R}` from the normalized profile map
`c_D(u)=Ctilde_D u / ||Ctilde_D u||_{H_Omega(D)}`.  The scalar spectral weights
and spectral measure now use `c_D(u_N)`, so the word "operator" is reserved for
the linear map.

Acceptance criteria:

- The normalization factor is not included in the linear scalarization
  operator.
- `mu_{nN}` is computed with the normalized profile `c_D(u_N)`.
- The text states that `c_D` is generally nonlinear, while `Ctilde_D` is linear
  under the stated Hermitian-pairing convention.

### R16. Interface Data Declaration

Priority: medium.
Status: completed.
Resolution: Core Structure now separates the Spin^c generation-theorem data
`D_gen=(C,R,L_R,scrD_R)` from the formation/visibility interface data
`D_int(D)=(pi_D,j_D,w_D,J_vis)`.  Section IX refers back to this interface-data
declaration and states explicitly that changing these data changes the
effective rates/overlaps, not the index-theoretic result `N_gen=3`.

Acceptance criteria:

- The paper explicitly lists the data required for the Spin^c multiplicity
  theorem.
- The paper separately lists the data required for scalarization and
  visibility.
- The text states that the interface data are not inputs to the generation
  count.

### R17. Self-Adjoint Scalar Realization

Priority: medium.
Status: completed.
Resolution: Section IX now states that `L_Omega(D)` is the Friedrichs
self-adjoint realization on `H_Omega(D)` for the regulated two-center
potential, or the corresponding finite-volume self-adjoint realization with
the stated boundary conditions. The projection-valued spectral measure
`dE_lambda(D)` used in the soft assignment is explicitly tied to this
self-adjoint operator.

Acceptance criteria:

- The paper specifies the self-adjoint realization of `L_Omega(D)`.
- The finite-volume convention is separated from the infinite-volume/Friedrichs
  convention.
- The projection-valued measure `dE_lambda(D)` is identified as the spectral
  measure of that operator.

### R18. Uniform Effective Formation Rate

Priority: medium-high.
Status: completed.
Resolution: The body probability law now uses `Gamma_N^eff(D,eta)` directly,
matching the abstract.  The text defines `Gamma_N^eff=Gamma_N` in the
hard-locking regime and `Gamma_N^eff=Gamma_N^soft` otherwise, then uses this
same effective rate in the Markovian formation ODE, its solution, and the
conditional probability formula.

Acceptance criteria:

- The final probability law uses `Gamma_N^eff(D,eta)` rather than the
  hard-locking-only `Gamma_N(D,eta)`.
- `Gamma_N` remains the Schur/WKB rate defined only in the hard-locking
  regime.
- The soft-assignment rate is incorporated through the single definition of
  `Gamma_N^eff`, not by a trailing replacement sentence.

### R19. Visibility Pairing Linearity Convention

Priority: low-medium.
Status: completed.
Resolution: The visibility section now states that, under the chosen
mathematical convention where the Hermitian pairing is antilinear in the first
entry, `y_N^eff` is an antilinear amplitude in the generation vector `u_N`.
Since `B_N` uses only `|y_N^eff|^2`, the normalized visibility is unchanged.
The text also notes that phase-sensitive Yukawa or Wilson-coefficient uses may
instead adopt the opposite pairing order `<J_vis,u_hat_N>` to obtain a
linear-in-`u_N` convention.

Acceptance criteria:

- The convention note appears immediately after the `y_N^eff` formula.
- The text states that `y_N^eff` is antilinear in `u_N` under the current
  Hermitian-pairing convention.
- The text states that using `<J_vis,u_hat_N>` gives a linear-in-`u_N`
  convention and leaves `B_N` unchanged.

### R20. Axis-Domain Caveat for `pi_D`

Priority: low-medium.
Status: completed.
Resolution: The projection-map subsection now states that the displayed
cylindrical representative for `zeta_R` is defined on
`R^3 \ A_ax`, where `A_ax={rho=0}` is the axial coordinate singularity.  The
text explains that `A_ax` has zero `dmu_cyl` measure for the visibility
integrals, so the pullback may be read in an `L^2` almost-everywhere sense, or
as the limit of a smooth axial phase regularization.

Add a short caveat near the explicit projection map

```text
zeta_R = sqrt(r_+/r_-) exp(i phi)
```

explaining that the cylindrical formula is defined away from the axial
coordinate singularity `rho=0`.  The axial set is measure zero for the
visibility integrals, and the pullback construction may equivalently be read
in an `L^2` almost-everywhere sense or as the limit of a smooth axial phase
regularization.

Acceptance criteria:

- The paper states that the displayed cylindrical formula for `pi_D` is defined
  on `R^3 \ {rho=0}` before extension/regularization.
- The text explains that the axial set does not affect the `L^2` visibility
  integrals.
- The text gives an acceptable interpretation: almost-everywhere pullback or
  smooth axial regularization.

### R21. Define the `O_vis` Functional

Priority: low-medium.
Status: completed.
Resolution: The visibility section now defines the linear functional
`O_vis: H_gen -> C` using the pairing order `<J_vis,pi_D^*u>`, so the
operator notation `O_vis^\dagger O_vis` is explicitly the induced rank-one
positive operator on `H_gen`.  The text states that this linear convention and
the invariant `y_N^eff` convention differ only by pairing order/conjugation and
give the same normalized `B_N`.

Define the operator notation used in the equivalent visibility formula.  The
cleanest convention is to define a linear functional

```text
(O_vis u) =
  y_0 int_{R^3} <J_vis, pi_D^*u>_{h_hat_R} dmu_cyl,
```

so that `O_vis: H_gen -> C` is the visible overlap functional and
`O_vis^\dagger O_vis` is the induced rank-one positive operator on
`H_gen`.  This should be connected explicitly to the already stated
anti-linear pairing convention: the current `y_N^eff` and the linear
`O_vis u_N` differ only by pairing order/conjugation convention and give the
same normalized `B_N`.

Acceptance criteria:

- The paper defines `O_vis: H_gen -> C` before using
  `O_vis^\dagger O_vis`.
- The definition uses the linear-in-`u` pairing order
  `<J_vis,pi_D^*u>`.
- The text states that this operator notation induces the same `B_N` as the
  invariant `y_N^eff` visibility formula.

### Post-R21 Freeze

Status: active.

After R20 and R21 are completed, stop changing the theory structure unless a
new concrete mathematical error is found.  The next phase should be limited to
final proofreading: layout, references, citation style, abstract/conclusion
tone, symbol consistency, and PDF visual QA.

### R22. PRD Figure and Table Integration

Status: completed.

Add the PRD submission figure/table layer as reader guidance, not as new
theory.  The figures should make the theorem boundary visually explicit:
`D_gen=(C,R,L_R,scrD_R)` proves the Spin^c family multiplicity, while
`D_int(D)=(pi_D,j_D,w_D,J_vis)` supplies only the post-index
formation/visibility interface.

Required main-text items:

- Fig. 1 `fig:logical_architecture`: logical architecture of the SM charge
  layer, protected Spin^c theorem layer, and post-index interface layer.
- Fig. 2 `fig:two_center_projection`: two-center spatial projection geometry,
  the branch points `p_+`, `p_-`, the divisor `R=p_+ + p_-`, and
  `L_R=O(R)=O(2)`.
- Fig. 3 `fig:index_chain`: index-theoretic proof chain from `R` and `L_R`
  to `Ker scrD_R^+`, `h^0=3`, `h^1=0`, and three SM family copies.
- Fig. 4 `fig:spinc_vs_spin`: Spin^c Dolbeault--Dirac carrier versus the
  ordinary spin Dirac counting shift.
- Fig. 5 `fig:toeplitz_basis`: Toeplitz moment-map operator as
  canonicalization of the three labels, not as a replacement for
  Riemann--Roch plus Serre duality.
- Fig. 6 `fig:post_index_interface`: scalar spectral and formation/visibility
  interface, explicitly marked as not an input to the proof of `N_gen=3`.
- Table 1 `tab:assumption_boundary`: assumption boundary and theorem scope.

Acceptance criteria:

- All six figure environments and Table I compile into `paper/main.pdf`.
- Captions consistently state which objects are theorem inputs, theorem
  consequences, and post-index effective data.
- The graphics remain black-and-white friendly and do not introduce new
  phenomenological claims.
- The final PDF text layer contains all six `FIG.` captions and `TABLE I`.

Verification:

- Added and compiled Fig. 1--Fig. 6 with labels
  `fig:logical_architecture`, `fig:two_center_projection`,
  `fig:index_chain`, `fig:spinc_vs_spin`, `fig:toeplitz_basis`, and
  `fig:post_index_interface`.
- Added and compiled Table I with label `tab:assumption_boundary`.
- Final PDF text-layer check found all six `FIG.` captions and `TABLE I`;
  spot-rendered pages 4, 5, 6, 11, 15, and 17 for visual QA.

### R23. PRD Submission Polish: Tone, Caveats, and Figure Layout

Status: completed.

This is a final submission-polish pass, not a new theory-structure task.
The goal is to reduce any remaining UV-parent-action overclaim, make small
mathematical caveats explicit, and clean up the figure layout after the PRD
figure/table integration.

Required edits:

- Rename Section II from `Parent Projection Data` to a softer projection-data
  title and replace `parent action` language by an effective bookkeeping
  decomposition.  The theorem should use the projection data and topological
  constraint, not claim a UV-complete parent action.
- Replace `exact no-fourth-generation theorem` wording by a conditional
  no-fourth-family statement within the protected SM-charged sector.
- Add the Hellinger-affinity explanation for `eta(D,epsilon)` and derive
  `0 <= eta <= 1` from Cauchy--Schwarz for normalized source densities.
- Add the nonzero visible-overlap assumption
  `sum_I |y_I^eff|^2 > 0` before using the normalized `B_N`.
- Clean up Fig. 2, Fig. 3/Fig. 4 float placement, and Fig. 6 readability.

Acceptance criteria:

- `paper/main.pdf` compiles without undefined references or citations.
- The PDF text layer still contains all six figures and Table I.
- Visual spot checks show the edited figures are not clipped or visually
  tangled.
- Local `PSLT_another_flow/paper/main.tex` and `main.pdf` are synced after
  compilation.

Verification:

- Renamed Section II and softened `parent action` into the effective
  bookkeeping decomposition `S_eff`; the text now explicitly says no
  UV-complete parent action is derived here.
- Replaced the exact no-fourth-generation phrasing by the conditional
  no-fourth-family statement within the protected SM-charged sector.
- Added the Hellinger-affinity / Cauchy--Schwarz explanation for `eta` and
  the nonzero-overlap condition for the normalized `B_N`.
- Cleaned Fig. 2 labels, inserted `FloatBarrier` around Fig. 3/Fig. 4, and
  rewrote Fig. 6 as a clearer two-layer post-index interface.
- Recompiled `paper/main.pdf`; text-layer checks found all six figures,
  Table I, and the new caveat language; visually spot-checked the changed
  figure pages.

### R24. Final PRD Candidate Micro-Polish

Status: completed.

This is the last small polish pass before treating the manuscript as a PRD
Regular Article candidate draft.

Required edits:

- Lower the conclusion wording from "the theory has exactly three..." to a
  conditional statement about the protected SM-charged generation sector.
- Add the denominator-positive domain for the conditional probability law
  `P_N(t;D,eta)`, including the `t -> 0^+` limit when at least one effective
  formation rate is positive.
- Reduce the Fig. 3/Fig. 4 float-induced whitespace without letting the
  ordinary-spin remark be split by figures.
- Add only minimal extra family/string-cohomology background references, if
  useful for the introduction.

Acceptance criteria:

- `paper/main.pdf` compiles without undefined references or citations.
- Final PDF text-layer checks show the new probability caveat, softened
  conclusion wording, and added references.
- The visually checked figure pages remain clean.

Verification:

- Conclusion wording now attributes the exact three-family result to the
  protected SM-charged generation sector under the stated projection and
  gap/exclusivity assumptions.
- Added the denominator-positive domain and the `t -> 0^+` rate-weighted
  conditional probability limit for `P_N(t;D,eta)`.
- Removed the post-Fig. 4 float barrier so the theorem text fills the former
  whitespace while keeping Fig. 3/Fig. 4 outside the ordinary-spin remark.
- Added two minimal heterotic Standard Model background references to the
  introductory compactification citation cluster.
- Recompiled the PDF and visually spot-checked pages 11--12.

### Final Proofreading Checklist

Status: active.

Use this checklist for the post-freeze pass.  These items are presentation and
consistency checks, not new theory tasks.

- Confirm that the abstract, main theorem, and conclusion all keep the
  conditional framing: `conditional on the PSLT two-center projection data`.
- Confirm that the paper consistently separates the two logical layers:
  `scrD_R` fixes the Spin^c generation count, while
  `(V_eff,Gamma_N^eff,B_N)` describe effective formation and visibility.
- Confirm that every no-fourth-generation statement includes, or clearly points
  back to, the exclusivity / vectorlike gap assumption for all other
  SM-charged sectors.
- Confirm that the "spin-1 Hilbert space" and Toeplitz-basis language is used
  only as interpretation of the `H^0(CP^1,O(2))` result, not as a substitute
  for the Riemann--Roch plus Serre-duality proof.
- Confirm that the one-family hypercharge section keeps the minimal-content,
  Yukawa-invariance, anomaly-cancellation, and normalization/global-group
  caveats.
- Confirm that the BPS-compatible Dolbeault motivation remains a short remark,
  not a new unconditional string/QG vacuum-selection theorem.
- Confirm final PDF presentation: page breaks, equation numbering, references,
  bibliography formatting, symbol consistency, and rendered overlines/accents.

## Do Not Reopen

- Do not restore comparison tables to the main paper.
- Do not claim an unconditional derivation of the full Standard Model.
- Do not use ordinary spin Dirac twisted only by `O(2)` to count three zero
  modes; it gives `H^0(CP^1,O(1))`.
- Do not use `ind D_vec = 0` alone as a no-light-exotics condition.
- Do not let the scalar spectral operator replace the Spin^c fermion zero-mode
  theorem for the generation count.
- Do not silently identify the Spin^c generation basis `u_N` with the scalar
  spatial eigenmodes `psi_n`; use the explicit scalarization weights
  `Ctilde_D, c_D, mu_{nN}` and introduce hard locking only under the gap
  condition.
- Do not use `psi_N` or `omega_N` in the abstract before the hard-locking
  condition has been stated.
- Do not call a normalization-dependent profile map linear; keep the raw
  scalarization operator separate from the normalized profile.
- Do not treat `(pi_D,j_D,w_D,J_vis)` as assumptions needed for the Spin^c
  index count; they belong to the effective formation/visibility layer.
- Do not use the scalar spectral measure `dE_lambda(D)` without specifying the
  self-adjoint realization of `L_Omega(D)`.
- Do not write the final body probability law with the hard-locking-only
  `Gamma_N`; use `Gamma_N^eff` and define its hard/soft cases.
- Do not treat the antilinearity of `y_N^eff` under the chosen Hermitian
  convention as a physical ambiguity in `B_N`; the normalized visibility uses
  `|y_N^eff|^2`.
- Do not use `O_vis^\dagger O_vis` without defining `O_vis` as the visible
  overlap functional on `H_gen`.
