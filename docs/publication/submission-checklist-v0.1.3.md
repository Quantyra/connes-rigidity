# Submission checklist — prepared v0.1.3-report

Date: 2026-10-28. **Prepared, unreleased version; publication gate pending.** The previous checklist and Dan's August approval are historical only. No new DOI, release or tag has been created.

Title: **Hypothesis failure for Ioana's Theorem 8.2 under a twisted comultiplication**
Author: Daniel Eric Fredriksen, Quantyra Inc.
Suggested categories: math.OA; optionally math.GR. MSC: 46L10, 46L35, 22D25, 03B35.
License: CC-BY-4.0 for Quantyra-authored manuscript and documentation.

## Candidate files

- [Six-page PDF](../notes/nielsen-ioana-theta-reductio-arxiv.pdf)
- [Authoritative TeX and abstract](../notes/nielsen-ioana-theta-reductio-arxiv.tex)
- [Long-form companion](../reports/2026-08-08-nielsen-ioana-theta-reductio-refutation.md)
- [Self-contained source ZIP](nielsen-ioana-theta-v0.1.3-source.zip) and [build instructions](source-bundle-v0.1.3-README.txt)
- [Artifact SHA256 manifest](artifact-manifest-v0.1.3.json)
- [Verification record and Lean coverage matrix](verification-v0.1.3.md)
- [Primary-source identities and page anchors](../sources/nielsen-2026-10-28-identity.md)

The immutable candidate is the science commit containing these artifacts; record its exact SHA in the parent review packet. The manifest uses file hashes rather than a self-referential commit hash. Prepared version: `v0.1.3-report`. The canonical remote was fetched and checked: main was `c2d61f5179507af2c2184d837ee9458e8d766a57`; latest remote tag was `v0.1.1-report`; the subsequent public deposit is v0.1.2-report. No existing version is overwritten.

## Author checks completed

- [x] Corrected general input and torsion-free/general conclusions of Theorem 8.2; no assertion that both coordinates are injective.
- [x] Visible revision note; response to all three defenses in Section 21 of the pinned 49-page Nielsen artifact.
- [x] Both mixed targets distinguished from single factors; acknowledged Nielsen's explicit right-target exclusion claim.
- [x] Retained Section 9 appeal treated separately as a hypothesis comparison.
- [x] Existing containment witness, Lean anchors, classical import and non-claims preserved.
- [x] Tectonic build and clean extraction/rebuild of the source bundle succeeded; references and layout checked; all six pages visually inspected.
- [x] Historical source pins retained; no new raw third-party PDF or private runtime logs bundled.
- [x] Citation and Zenodo metadata identify a prepared, unreleased version with no new DOI; historical DOI explicitly historical.

## Repair status — 28 October 2026

- [x] M1 placeholder/definitional qualification in abstract, Section 6, table and coverage record.
- [x] L1/L2 scope and conclusion alignment; N1 witness notation; N2 exact pages; optional N4 witness clarification.
- [x] Non-claims minors: explicit placeholder coverage and dated historical bridge notice.
- [x] N3 parent primary-source confirmation retained: Popa pp.809–899; direct Ioana criterion citation unchanged.

Early findings at `7ee23d1dc88f435725cfc20e576d49a5d30a58a2` remain preserved in Git and are resolved by the recorded rechecks below. The final manuscript and fresh Lean role PASSes are recorded below; targeted successor-prose review and the parent aggregate gate remain pending. Author preparation is not reviewer signoff.

## Required closeout — pending

- [x] Proof-adversarial, non-claims and package/metadata final PASSes at `9aba11a39d6fba5886f0c1cbd73408290b15339e`.
- [x] Independent Lean/build/audit PASS at the same science commit, accepting corrected canonical source `c1e6dfb7347261336714e57de86e6f25c7627461`, fresh target build, twelve kernel profiles and statement match; operational closure checked separately.
- [x] Historical full 3188-job CI remains separate support; fresh target is `ConnesRigidity.NielsenThetaImage`, not a full-project build.
- [x] Final PDF/TeX/ZIP and all four bundle-member identities preserved; no rebuild or mathematical/source/coverage change in this evidence-only successor.
- [ ] Targeted independent Lean acceptance of the new public verification prose and exact successor diff.
- [ ] Parent metadata/hash/link/scope check of the exact successor; record conditional docs-only carryforward of the original three PASSes, without attributing unseen-byte review to those reviewers.
- [ ] Parent records exact successor commit, all four role scopes and aggregate release decision in its publication packet.
- [ ] Separate human approval before arXiv submission or outreach; neither is part of version production.
- [ ] Ordinary GitHub release only after required gates; no additional human approval is a prerequisite for already-authorized version production. No publication action is part of this preparation. Record a new DOI only if actually issued; do not assign the v0.1.2 DOI to new bytes.

Historical science DOI: https://doi.org/10.5281/zenodo.21859653 (v0.1.2-report). Science concept DOI: https://doi.org/10.5281/zenodo.21845586. Lean v0.1.1-obstruction DOI: https://doi.org/10.5281/zenodo.21859309.
