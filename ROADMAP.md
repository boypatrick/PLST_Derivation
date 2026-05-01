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
defines the scalarization operator `C_D:H_gen -> H_Omega(D)`, introduces
spectral weights `mu_{nN}=|<psi_n,C_D u_N>|^2`, and treats the hard map
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
Resolution: The hard locking map is now derived only after defining `C_D`,
the scalar spectral weights `mu_{nN}`, and the gap condition
`mu_{n(N),N} - sup_{m != n(N)} mu_{mN} >= Delta_lock`.  If the gap condition
fails, the paper uses a soft assignment
`Gamma_N^soft=sum_n mu_{nN} Gamma_n`, or the corresponding spectral-measure
integral for continuous spectrum.

Acceptance criteria:

- `u_N`, `u_hat_N`, and `psi_n` live in explicitly distinct spaces.
- The interface from generation zero modes to scalar profiles is `C_D`, not a
  silent identification of bases.
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
  `C_D, mu_{nN}` and introduce hard locking only under the gap condition.
- Do not use `psi_N` or `omega_N` in the abstract before the hard-locking
  condition has been stated.
