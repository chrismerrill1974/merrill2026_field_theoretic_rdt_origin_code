# Radial Dimensionality Theory VI: A Field-Theoretic Origin for the Density-Dependent Gravitational Coupling

Scientific source and reproducible results for version v2.

- [Paper](reproduction/output/pdf/publication/paper6/merrill_rdt_field_theoretic_origin_v2.pdf)
- [Manuscript](reproduction/paper6/V1_Paper/paper6_v1.tex)

## Reproduction

Requires Python 3.14, NumPy 2.4.2, SciPy 1.17.1, Matplotlib 3.10.8,
TeX Live with revtex4-2, and Poppler. The resource controller uses POSIX
nice/setpriority, SIGPROF and SIGSTOP/SIGCONT.

The current reproduction environment is pinned in
[`requirements-reproduction.txt`](requirements-reproduction.txt). The original
`requirements.txt` belongs to the historical top-level scripts. Install the
current Python dependencies in an isolated Python 3.14 environment with
`python3 -m pip install -r requirements-reproduction.txt`.

From the repository directory:

```sh
nice -n 19 python3 reproduce.py --output /tmp/merrill2026_field_theoretic_rdt_origin_code-reproduction
```

The output directory must not exist. This verifies every capsule checksum,
regenerates tables, figures or algebraic checks from retained scientific outputs,
and builds a PDF whose extracted text matches the included paper.
No parameter scan runs in this command. Full scientific runs use the producing
scripts and their data under `reproduction/`. Use one worker, verified nice 19,
at most 95% of one CPU and one native-library thread.

`release.json` identifies the current manuscript and PDF;
`reproduction/CAPSULE.json` binds the scientific source and data by checksum.
Shared dependencies and saved results are included so no sibling checkout is
required. Historical top-level scripts and data retain their original identity;
the current paper and source manifest distinguish them from the revised results.

## Scientific scope

This version retains the published title, but does not establish the field-theoretic origin named in it. The proposed positive-density equilibrium fails the equations of the written scalar action, so the revision audits a failed candidate derivation and withdraws the claimed origin and equivalence between local coupling and the weighted radial operator. The action remains as an audited candidate; earlier local-coupling stellar diagnostics are not solutions of the full scalar stellar problem. This failure does not exclude the separately specified phenomenological operator model or every possible field-theoretic completion.
