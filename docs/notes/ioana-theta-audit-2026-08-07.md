# S006 — Ioana / Θ hypothesis audit

**Date:** 2026-08-07  
**Epic:** E005  
**Verdict (local gate only):** **REVISE** (Nielsen route) · **NO-GO** for “Ioana alone proves Connes / kills all counterexamples”  
**NON-CLAIMS:** Does **not** assert Connes true or false. Does **not** assert OpenAI/Zhou invalid or valid.

---

## 1. Scope of this memo

Decide only:

> Does Ioana’s Bernoulli W*-superrigidity / classification package produce the injective \(\delta_2\) needed by a Nielsen-style reductio from bare \(L(G)\cong L(H)\) via a twisted comultiplication \(\Theta\)?

Not decided: global Connes; OpenAI/Zhou correctness.

## 2. Sources used

| Source | Role | Status |
|--------|------|--------|
| Ioana JAMS 2011 DOI 10.1090/S0894-0347-2011-00706-6 | Classical Ioana | Bib pin only — **no fulltext** |
| Zhou arXiv:2608.02327 | Counterexample claim; cites [Ioa11] as background | PDF pinned |
| OpenAI ten-proofs @ `94bc0feb` + paper PDF | Counterexample claim; cites [Ioa11] as Bernoulli W*-superrigidity | Pinned |
| Nielsen PhilPapers NIEWTC | \(\Theta\) definition owner | **Blocker — 403 / no fulltext** |
| Sol Pro / Grok chat | Attack surface only | Advisory |

## 3. B1 — Reconstruct \(\Theta\)

**From Nielsen intake sketch only** (not primary text):

\[
\Theta(f u_g) = f u_g \otimes \Phi(u_g)
\]

built from assumed \(\Phi: L(G)\to L(H)\) factor isomorphism, on a Bernoulli crossed product \(A_G = L^\infty(X)\rtimes G\).

**Status:** Definition card is **intake-level only**. Cannot certify against Nielsen primary manuscript → contributes to **REVISE**.

## 4. B2 — Ioana hypothesis checklist (structural)

Until fulltext, checklist is **structural** (OpenAI/Zhou narrative + standard OA knowledge), not Pass/Fail from quotes.

| Hypothesis (expected class) | Bare \(L(G)\cong L(H)\) | Nielsen \(\Theta\) route | OpenAI/Zhou CE route |
|----------------------------|-------------------------|---------------------------|----------------------|
| Working in Bernoulli GMS crossed product | Not automatic | Assumed by construction | Not the CE claim surface |
| Source relative (T) / Bernoulli of (T) group | N/A | Claimed if \(G\) has (T) | N/A for bare factors |
| Non-intertwining (no bad tensor leg) | N/A | **Contested** (Sol Pro vs Nielsen/Grok) | N/A |
| Hom form covered by Ioana thm statement | N/A | Contested — need Thm 8.2/C text | N/A |
| Output \(\delta_2\) injective group hom | N/A | Desired | N/A |
| Ioana ⇒ Connes for all ICC+(T) pairs | **No** | **No** | **No** |

## 5. B3 — Sol Pro bad-leg claim

**Claim:** \(\Theta(A_G)\subseteq A_G\bar\otimes L(H)\) ⇒ Ioana NI fails.

**Assessment without Ioana fulltext + Nielsen fulltext:**

- Logically coherent **attack** on the NI route.
- Grok status: Ioana may allow targets \(M\bar\otimes N\) for finite \(N\); issue is whether NI holds, not whether the category of homs is empty.
- **Cannot mark Pass or Fail** on NI without paper text → **Unknown**.

Lean already owns: *if* bad-leg holds *and* interface axiom `solProBadLeg_implies_not_nonIntertwining`, then Nielsen Ioana gate fails (`solPro_block_negates_nielsen_gate`).

## 6. B4 — Nielsen uniform NI / deformation / Cartan

**Claim (intake):** Bernoulli deformation fixes group unitaries; \(\Theta(L^\infty(X))=L^\infty(X)\otimes 1\) independent of \(\Phi\); only rigid case survives.

**Assessment:** Not checkable without Nielsen + Ioana fulltext. Status **Unknown**. Contributes to **REVISE**.

## 7. B5 — Verdict

### Local gate on Nielsen Ioana step

| Option | Decision |
|--------|----------|
| GO (Nielsen route fires) | **No** — premises not discharged from primary text |
| NO-GO (NI route blocked as theorem) | **No** — Sol Pro obstruction not established from primary text |
| **REVISE** | **Yes** — missing Nielsen fulltext + Ioana fulltext verbatim hypotheses |

### Broader logical NO-GOs (do hold as Quantyra meta-claims; Lean-backed)

These are **not** Connes verdicts:

1. **Ioana Bernoulli W*-superrigidity does not equal Connes group-factor rigidity.**  
   OpenAI and Zhou themselves present CE at the **group factor** level while citing Ioana as action/crossed-product background.  
2. **Pair-local reductio ≠ universal Connes** — Lean: `connes_iff_not_counterexample`, pair schemas.  
3. **Failed NI interface ⇒ no rigidSuccess via NI route** — Lean: `failed_NI_is_not_rigidSuccess`, `solPro_block_negates_nielsen_gate`.

### Implication for Phase D

Phase D (Borel–Margulis–Schur–Bockstein) is **PARKED** until S006 exits REVISE with GO, **or** until a different (non-Nielsen) path is chartered.

## 8. B6 — Lean

No new discharge of interface axioms this memo (still need classical text). Meta-logic core remains green. Optional follow-up: add `docs/notes` pointer theorem names only.

## 9. Required follow-ups

1. Obtain Nielsen primary PDF/HTML.  
2. Obtain Ioana JAMS fulltext; quote Thm C / 8.2 / Cor 2.3.  
3. Re-open S006 for Pass/Fail NI rows.  
4. Continue S007 OpenAI rebuild audit independently of Nielsen.
