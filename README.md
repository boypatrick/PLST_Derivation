# PLST Derivation

This repository contains the clean first-principles three-generation derivation manuscript.

## Contents

- `paper/main.tex` - LaTeX source for the derivation.
- `paper/main.pdf` - compiled PDF.

The core claim is that the three Standard Model generations arise from the Spin^c
Dolbeault-Dirac operator on the two-center projection bundle.  The divisor
`R = p_+ + p_-` on `CP^1` gives `L_R = O(R) = O(2)`, and

```text
Ker D_R^+ ~= H^0(CP^1, O(2)),   Ker D_R^- ~= H^1(CP^1, O(2)).
```

Riemann-Roch and Serre duality then give `h^0 = 3` and `h^1 = 0`, provided no
additional SM-charged nonzero-index sector is present.
