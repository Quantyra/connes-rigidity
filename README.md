# Quantyra-Connes-Rigidity

Science / reconstruction satellite for the Quantyra Jenny Connes rigidity audit.

## Prepared version: v0.1.3-report — 28 October 2026

**Hypothesis failure for Ioana's Theorem 8.2 under a twisted comultiplication**, Daniel Eric Fredriksen.

- [Revised PDF](docs/notes/nielsen-ioana-theta-reductio-arxiv.pdf) · [TeX](docs/notes/nielsen-ioana-theta-reductio-arxiv.tex)
- [Long-form report](docs/reports/2026-08-08-nielsen-ioana-theta-reductio-refutation.md)
- [Source bundle](docs/publication/nielsen-ioana-theta-v0.1.3-source.zip) · [checklist](docs/publication/submission-checklist-v0.1.3.md) · [verification and Lean coverage](docs/publication/verification-v0.1.3.md)
- [Source identity and page anchors](docs/sources/nielsen-2026-10-28-identity.md)

This revision corrects our overstatement of Theorem 8.2's input and injectivity conclusion, addresses all three defenses in Nielsen's 49-page Section 21, and separately compares the hypotheses of the retained Section 9 appeal. The existing containment-to-intertwining obstruction remains bounded to this theorem application.

**Prepared, unreleased version; publication gate pending.** Four independent role PASSes at `9aba11a` and the remaining targeted successor evidence/metadata checks are recorded in the [verification record](docs/publication/verification-v0.1.3.md). No tag, release, upload or version DOI exists for this version. Production of this version is authorized; arXiv submission and outreach require separate human approval. Historical approval does not approve these bytes.

## Historical deposit and Lean companion

Previous public science version: [v0.1.2-report, DOI 10.5281/zenodo.21859653](https://doi.org/10.5281/zenodo.21859653). [Science concept DOI](https://doi.org/10.5281/zenodo.21845586).

Lean: [v0.1.1-obstruction](https://github.com/Quantyra/connes-rigidity-lean/tree/v0.1.1-obstruction), SHA `c1e6dfb7347261336714e57de86e6f25c7627461`, [version DOI](https://doi.org/10.5281/zenodo.21859309). The concrete Nielsen image situation is classically imported; containment-to-intertwining and hypothesis failure are proved on a semantic interface. An independently accepted fresh build of `ConnesRigidity.NielsenThetaImage` and twelve-declaration kernel audit are recorded in the verification record. This is a targeted build; the classical-import and partial semantic coverage limits remain unchanged.

## Non-claims

This report does not decide Connes rigidity or the validity of OpenAI/Zhou counterexamples. Non-licensing of output by this application does not assert nonexistence of group morphisms or impossibility of other routes.

Canonical repositories: [science](https://github.com/Quantyra/connes-rigidity), [Lean](https://github.com/Quantyra/connes-rigidity-lean). Theorem development belongs in the Lean satellite; this revision introduces no new theorem or Lean code.
