# Field-Theoretic Origin Code — Radial Dimensionality Theory VI

Companion repository for **Radial Dimensionality Theory VI: A Field-Theoretic
Origin for the Density-Dependent Gravitational Coupling**
(C. K. Merrill and Claude, 2026).

Paper VI gives RDT an action. The key claim is that, in the regime where RDT
acts (dense matter, with vacuum reducing to general relativity), the series'
divergence operator is operationally a **density-dependent effective
gravitational coupling**

    G_eff(rho) = 3 G_N / d_eff(rho) = G_N / (1 - sigma),
    sigma = A x/(1+x),  x = (rho/rho0)^alpha,  rho0 = 150 g/cm^3,

realized by a single non-minimally coupled scalar field sigma (the
dimension deficit), with the contraction sign built in, alpha free, the
saturation floor emergent, and vacuum = GR by construction. This repository
holds the two numerical checks behind the paper. (The stability, c_GW = c, and
conformal-frame results are analytic; see the manuscript.)

## Requirements

Python >= 3.8 with `numpy`, `scipy`.

## Contents

| File | Purpose |
|---|---|
| `u_sigma.py` | **The potential.** Shows the one-parameter potential `U'(sigma) = lambda [sigma/(A-sigma)]^(1/alpha)` reproduces the series saturating law `sigma_eq(rho) = A x/(1+x)` to machine precision, for alpha = 0.12, 0.30, 0.50, 1.0 (outer crust -> NS core); U is convex (tachyon-free) and the sigma->A wall gives the floor `d_eff > 2.974`. Demonstrates **alpha is a free shape parameter, not forced to 1**. |
| `geff_check.py` | **The stellar limit.** Integrates TOV with `dP/dr` multiplied by the action's coupling factor `G_eff(rho)/G_N = 1/(1 - A x/(1+x))`, and confirms it reproduces Paper III V8's divergence-operator contraction (M_max -0.6%, R(1.4) -0.3% vs the operator's -0.71%/-0.42%) and is opposite in sign to the early force-rescaling ansatz (+0.9%, expansion). The ~0.1 pp gap to the full operator is the genuinely-dimensional, non-local piece a local field omits. Gate: A=0 reproduces the GR baseline. |
| `eos.py`, `tov.py` | SLy equation of state (CompOSE crust-to-core table) and baseline TOV solver — the same gate-validated modules as the Paper III repo (`merrill2025_neutronstar_code`). |
| `data/` | CompOSE RG(SLY4) table (`eos.thermo`, `eos.nb`, reference curve `eos.mr`) and the Douchin & Haensel table. |

## Usage

```sh
export OMP_NUM_THREADS=1 OPENBLAS_NUM_THREADS=1 MKL_NUM_THREADS=1 \
       VECLIB_MAXIMUM_THREADS=1 NUMEXPR_NUM_THREADS=1

python3 u_sigma.py     # potential -> saturating law, alpha free (instant)
python3 geff_check.py  # stellar limit -> contraction reproduces III V8 (seconds)
```

## Related repositories

The stellar machinery (`eos.py`, `tov.py`, `data/`) is shared with the Paper III
repository `merrill2025_neutronstar_code`, whose full divergence-operator solver
(`tov_operator.py`) produces the -0.71% / -0.42% result this paper's coupling
reproduces to within ~0.1 pp. Paper V's black-hole results (`merrill2025_-
blackholes_code`) are inherited by construction here, since `G_eff -> G_N` in
vacuum.

## License

MIT — see [LICENSE](LICENSE).
