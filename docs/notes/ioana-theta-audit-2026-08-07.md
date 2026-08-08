# S006 — Ioana / Θ hypothesis audit (fulltext re-open)

**Date:** 2026-08-07 (updated after Nielsen NIEWTC + Ioana JAMS fulltext)  
**Prior status:** REVISE (missing fulltext)  
**Current local verdict:** **NO-GO** for Nielsen’s application of Ioana Theorem 8.2 to the twisted comultiplication \(\Theta\) to obtain rigid-case \(\delta_2\)  
**NON-CLAIMS:**  
- Does **not** assert Connes true or false.  
- Does **not** assert OpenAI/Zhou counterexamples are valid.  
- Does **not** audit Nielsen’s separate Lean code-internal ICC/(T) objections (track under S007).  
- Does **not** claim Ioana is false.

---

## 1. Primary sources (pinned)

| Source | Path | SHA256 |
|--------|------|--------|
| Ioana JAMS 2011 | `docs/sources/ioana-2011-jams-S0894-0347-2011-00706-6.pdf` | `0EF129649596FC6BDF36A7ADA3C1972CF1B20FB838D5E560D1FCACCEF21501E3` |
| Nielsen NIEWTC | `docs/sources/nielsen-NIEWTC.pdf` | `9529E43EBFF1E38A808397DA0C0FC56CABCB71C41B622FABA54B6B57573D3884` |
| Ioana pin quotes | `docs/literature/ioana-2011-pin.md` | — |
| Nielsen card | `docs/reconstruction/nielsen-NIEWTC-reconstruction-card.md` | — |

---

## 2. B1 — \(\Theta\) definition (from Nielsen primary)

\[
\Theta(f u_g) = f u_g \otimes \Phi(u_g),\qquad
\Phi:L(G)\xrightarrow{\sim} L(H),
\]
on Bernoulli crossed product \(A_G=L^\infty(X)\rtimes G\), landing in \(A_G\bar\otimes A_H\) (Nielsen: second leg carries \(\Phi(u_g)\in L(H)\)).

**Containment (Nielsen Remark 21, and by definition):**
\[
\Theta(A_G)\subseteq A_G\bar\otimes L(H).
\]

---

## 3. B2 — Ioana Theorem 8.2 hypotheses (verbatim structure)

From Ioana fulltext (Thm 8.2, pp. 1207–1208), for \(\theta:N\to M=M_1\bar\otimes M_2\) with Bernoulli \(M_i=B_i\rtimes\Gamma_i\):

**(1)** \(\theta(L(\Lambda_0))\nprec L(\Gamma_1)\otimes 1\) and \(\theta(L(\Lambda_0))\nprec 1\otimes L(\Gamma_2)\).  
**(2)** \(\theta(N)\nprec L(\Gamma_1)\bar\otimes M_2\) and \(\theta(N)\nprec M_1\bar\otimes L(\Gamma_2)\).

Only then does the rigid/standard conclusion (character + group homs + unitary) apply (torsion-free case; torsion case still requires these non-intertwinings).

Theorem C (intro) is the \(M\to M\bar\otimes M\) sibling with the same pattern of “bad legs” (1)(2) vs rigid (3).

---

## 4. B3–B4 — Checklist for Nielsen’s \(\Theta\)

Identify Nielsen’s setup with Thm 8.2 by taking:
- \(N = A_G\), \(\Lambda=G\), \(\Lambda_0=G\) (property (T) ⇒ relative (T) to itself),
- \(M_1=A_G\), \(M_2=A_H\), \(\Gamma_1=G\), \(\Gamma_2=H\),
- \(\theta=\Theta\).

| Hyp | Required | Status for \(\Theta\) | Evidence |
|-----|----------|----------------------|----------|
| (H) Bernoulli + rel (T) source | Yes | **Plausible** if \(G\) has (T) and action Bernoulli | Nielsen Prop. 20; standard |
| (1) NI on \(L(\Lambda_0)\) into group legs | Yes | **Unknown / contested** | Needs deformation argument; not decided here |
| (2) \(\theta(N)\nprec M_1\bar\otimes L(\Gamma_2)\) | Yes | **FAIL** | \(\Theta(A_G)\subseteq A_G\bar\otimes L(H)=M_1\bar\otimes L(\Gamma_2)\) ⇒ intertwining/containment into the forbidden leg |
| (2) other conjunct \(\nprec L(\Gamma_1)\bar\otimes M_2\) | Yes | Not needed once one conjunct fails | — |
| Rigid Case (III) / \(\delta_2\) from 8.2 | Requires (1)+(2) | **Not obtained from Thm 8.2** | Hypothesis failure |

**On Nielsen’s claim that NI holds uniformly:**  
Nielsen argues deformation fixes \(\Theta(u_g)\) and Cartan image \(L^\infty(X)\otimes 1\) kills Cases (I)(II). Even granting those arguments for (1) and Cartan-type conditions, they do **not** remove the **literal containment** \(\Theta(A_G)\subseteq M_1\bar\otimes L(H)\), which is exactly the negation of the second half of Ioana’s hypothesis (2).

Nielsen Remark 21 acknowledges the containment into the group-algebra leg and treats it as “target alignment,” not collapse. Under Ioana’s published wording, that containment is precisely a **failed hypothesis**, not a harmless alignment.

**On Nielsen’s misstatement risk:**  
Prop. 20 initially suggests Thm 8.2 has “no hypothesis on \(\theta\) beyond unitality,” then correctly notes NI prerequisites. The decisive published content is Thm 8.2’s (1)(2), not the abstract’s informal wording.

---

## 5. B5 — Verdict

### Local gate (Nielsen Ioana step)

| Question | Verdict |
|----------|---------|
| Does Ioana Thm 8.2 apply to this \(\Theta\) and yield rigid \(\delta_2\)? | **NO-GO** |
| Sol Pro “bad tensor leg” obstruction | **Sustained** by Ioana fulltext + Nielsen’s own containment |
| Grok “open whether NI holds” | **Closed for hyp (2):** fails by construction; hyp (1) may remain subtle but is moot |
| Phase D (Borel–Margulis–Schur–Bockstein) via this Ioana step | **PARKED / blocked** — no \(\delta_2\) from 8.2 |

### What this does *not* decide

| Claim | Status |
|-------|--------|
| Connes rigidity true | **Not proved** (Nielsen Part II uses the same failed gate) |
| Connes rigidity false | **Not proved** |
| OpenAI CE valid | **Open** (needs rebuild + def fidelity; Nielsen code objections separate) |
| Zhou CE valid | **Open** (reconstruction card only) |
| Nielsen code-level ICC/(T) kills of OpenAI | **Open** — track as independent audit items |

### Meta-logic (already Lean-owned)

- Pair reductio ≠ universal Connes.  
- If NI/hyp fails ⇒ no rigidSuccess via that Ioana route (`solPro_block_negates_nielsen_gate`).

---

## 6. B6 — Lean

Update `S006Status` to `.noGo` with comment pointing at this memo. Keep interface axioms; do **not** delete them (still document the contested claims). Optional later: add a theorem formalizing “containment in \(M_1\otimes L(\Gamma_2)\) ⇒ not hyp (2)” at the abstract interface level.

---

## 7. Recommended next work

1. **OpenAI rebuild audit** at `94bc0feb` (ICC/(T)/factor defs).  
2. **Zhou** independent check of Props 3.4 / 4.8 / 5.3 / 6.5.  
3. **Nielsen Part I code objections** — separate card, Lean object map.  
4. Do **not** publish “Connes proved” or “CE dead via Nielsen reductio.”  
5. Optional metalogic Zenodo still INTEGRITY-only.
