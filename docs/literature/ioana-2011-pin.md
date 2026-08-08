# Literature pin: Ioana (intended 2011 W*-superrigidity) — BLOCKER

**Pin date:** 2026-08-07  
**Intended target (from Zhou [Ioa11] and standard citation):**  
Adrian Ioana, *W\*-superrigidity for Bernoulli actions of property (T) groups*,  
J. Amer. Math. Soc. **24** (2011), no. 4, 1175–1226.  
doi:10.1090/S0894-0347-2011-00706-6  

**Requested local path:** `docs/sources/ioana-0910.3900.html` (+ companion PDF)

---

## BLOCKER — wrong paper under `ioana-0910.3900.*`

### What is on disk

| Path | Actual content |
|------|----------------|
| `docs/sources/ioana-0910.3900.html` | **Exists**, but is ar5iv/HTML for **arXiv:0910.3900** = *SQUID Detection of Quantized Mechanical Motion* (Pugnetti–Blanter–Fazio, cond-mat.mes-hall), **not** Adrian Ioana |
| `docs/sources/ioana-0910.3900.pdf` | Same wrong paper (SQUID / NEMS) |
| `docs/sources/ioana-1007.1408.pdf` | **Wrong:** Merkel–Schäfer, CMB gravitational lensing (astro-ph.CO) |
| `docs/sources/ioana-1010.5195.pdf` | **Wrong:** Glazyrin–Blinnikov, SNIa flame (astro-ph.HE) |

### What this pin therefore cannot do

- **Cannot** extract Theorem C / Theorem 8.2 / Corollary 2.3 (or nearest equivalents) with **verbatim** hypothesis lists from Ioana 2011 — those statements are **not present** in the downloaded HTML/PDF bodies.
- **Cannot** quote Ioana’s non-intertwining conditions from primary text.
- **Cannot** determine from primary text whether targets of the form `M → M ⊗̄ N` (arbitrary finite von Neumann algebra N) are in scope for the relevant intertwining / rigidity theorems.

### Attempted recovery

- arXiv API / nearby-id probes for the correct Ioana 2011 e-print were **rate-limited / timed out** during this session.
- Zhou’s bibliography only gives the **journal** citation for [Ioa11], not an arXiv number:
  > [Ioa11] Adrian Ioana. W\*-superrigidity for Bernoulli actions of property (T) groups. J. Amer. Math. Soc., 24(4):1175–1226, 2011. doi:10.1090/S0894-0347-2011-00706-6
- Note: arXiv id `0910.3900` is almost certainly a **off-by-digit / wrong-id download** relative to whatever e-print (if any) was intended; the HTML `og:url` confirms it is literally `https://ar5iv.labs.arxiv.org/html/0910.3900`.

### Required unblock

1. Obtain the correct Ioana 2011 source (journal PDF and/or correct arXiv e-print HTML).
2. Replace or add files under a non-misleading name (e.g. `ioana-jams-2011-w-superrigidity.pdf` + matching HTML if available).
3. Re-run pin extraction for:
   - full bibliographic pin (arXiv id if any, MSC, abstract);
   - **verbatim** statement + hypothesis list for Theorem C / Thm 8.2 / Cor 2.3 (or paper-internal numbering);
   - non-intertwining (`⊀` / “does not intertwine into”) conditions;
   - scope for embeddings/intertwiners into `M ⊗̄ N` for arbitrary finite N.

---

## Full bibliographic pin (journal only — from Zhou + JAMS citation string)

| Field | Value | Confidence |
|--------|--------|------------|
| Author | Adrian Ioana | High (Zhou + standard) |
| Title | W\*-superrigidity for Bernoulli actions of property (T) groups | High |
| Journal | Journal of the American Mathematical Society | High |
| Volume / pages / year | 24 (2011), no. 4, 1175–1226 | High (Zhou bib) |
| DOI | 10.1090/S0894-0347-2011-00706-6 | High (Zhou bib) |
| arXiv id | **Unknown / not verified in this repo** | Blocker |
| Local verified fulltext | **None** | Blocker |

### How Zhou uses [Ioa11] (secondary only)

From Zhou arXiv:2608.02327 introduction (reconstruction context only):

> “…W\*-superrigidity results for group actions, notably Ioana’s theorem for Bernoulli actions of property (T) groups [Ioa11].”

No theorem number, hypothesis list, or intertwining-target discussion is reproduced in Zhou beyond that one-line historical pointer. **Do not treat this as a substitute for Ioana’s statements.**

---

## Theorem C / Theorem 8.2 / Corollary 2.3 — VERBATIM extraction

**Status: NOT AVAILABLE from local sources.**

```
[BLOCKER] Verbatim hypothesis lists: MISSING
Reason: docs/sources/ioana-0910.3900.html is not Ioana 2011;
        companion "ioana-*.pdf" files are unrelated arXiv papers.
```

Placeholder for future fill-in (do not invent):

### Theorem C (numbering TBD)
- Statement: _TBD from correct source_
- Hypotheses (verbatim): _TBD_

### Theorem 8.2 (numbering TBD)
- Statement: _TBD_
- Hypotheses (verbatim): _TBD_

### Corollary 2.3 (numbering TBD)
- Statement: _TBD_
- Hypotheses (verbatim): _TBD_

---

## Non-intertwining conditions — what they say

**Status: NOT EXTRACTABLE from local Ioana files.**

Expected topic class (for unblock checklist only — **not** a claim about Ioana’s text):

- In Popa deformation/rigidity literature, “A does not intertwine into B inside M” (`A ⊀_M B`) is a technical non-embedding condition on corners of bimodules / partial isometries implementing intertwiners.
- Without the correct paper, this pin **refuses** to state Ioana’s precise non-intertwining hypotheses, quantifiers (e.g. over subalgebras of the base, group-measure-space Cartan, etc.), or conclusions (cocycle superrigidity / W\*-superrigidity form).

---

## Scope: targets of the form M → M ⊗̄ N (arbitrary finite N)?

**Status: UNRESOLVED — primary text missing.**

| Question | Answer from local sources |
|----------|---------------------------|
| Does Ioana 2011 treat intertwiners/embeddings into `M \bar\otimes N` for arbitrary finite von Neumann N? | **Unknown** (no correct fulltext) |
| Any local PDF/HTML sentence affirming or denying that scope? | **No** (wrong papers only) |

Unblock must quote the relevant theorem(s) and note whether N is:
- trivial / ℂ only,
- abelian,
- hyperfinite,
- or arbitrary finite.

---

## Wrong-file fingerprints (so future agents do not re-use them as Ioana)

| File | Opening title (pdftotext / HTML) |
|------|----------------------------------|
| `ioana-0910.3900.*` | “SQUID Detection of Quantized Mechanical Motion” — Pugnetti, Blanter, Fazio |
| `ioana-1007.1408.pdf` | “Gravitational lensing of the cosmic microwave background by nonlinear structures” — Merkel, Schäfer |
| `ioana-1010.5195.pdf` | “Propagation of thermonuclear flame in SNIa” — Glazyrin, Blinnikov |

---

## NON-CLAIMS

- This pin does **not** restate or endorse any Ioana theorem as verified.
- This pin does **not** claim arXiv:0910.3900 is Ioana’s paper (it is not).
- Secondary mention in Zhou is **not** a substitute for primary hypothesis lists.

## Next action

Download the correct Ioana JAMS 2011 / matching e-print into `docs/sources/`, then rewrite this pin with verbatim Theorem C / 8.2 / 2.3 blocks and an explicit yes/no on `M \bar\otimes N` scope.

**END OF PIN (BLOCKED)**
