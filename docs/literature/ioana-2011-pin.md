# Ioana 2011 pin — fulltext acquired

**Status:** Fulltext pinned.  
**Date:** 2026-08-07  
**Local PDF:** `docs/sources/ioana-2011-jams-S0894-0347-2011-00706-6.pdf`  
**PDF SHA256:** `0EF129649596FC6BDF36A7ADA3C1972CF1B20FB838D5E560D1FCACCEF21501E3`  
**Text extract:** `docs/sources/ioana-2011-jams.txt`

## Bibliographic pin

| Field | Value |
|-------|--------|
| Author | Adrian Ioana |
| Title | W*-superrigidity for Bernoulli actions of property (T) groups |
| Journal | *J. Amer. Math. Soc.* **24** (4): 1175–1226, 2011 |
| DOI | 10.1090/S0894-0347-2011-00706-6 |

## Theorem C (intro form, torsion-free; p. 1179)

> **Theorem C.** Let \(M = L^\infty(X)\rtimes\Gamma\) be as in Theorem A. Let \(\theta: M\to M\bar\otimes M\) be a (not necessarily unital) *-homomorphism and assume that \(\Gamma\) is torsion free.  
> Then one of the following holds true:  
> (1) \(\theta(L(\Gamma_0))\prec_{M\bar\otimes M} L(\Gamma)\otimes 1\) or \(\theta(L(\Gamma_0))\prec_{M\bar\otimes M} 1\otimes L(\Gamma)\).  
> (2) \(\theta(M)\prec_{M\bar\otimes M} L(\Gamma)\bar\otimes M\) or \(\theta(M)\prec_{M\bar\otimes M} M\bar\otimes L(\Gamma)\).  
> (3) \(\theta\) is unital and we can find a character \(\eta\) of \(\Gamma\), two group morphisms \(\delta_1,\delta_2:\Gamma\to\Gamma\) and a unitary \(u\in M\) such that \(u\theta(L^\infty(X))u^*\subset L^\infty(X)\bar\otimes L^\infty(X)\) and \(u\theta(u_g)u^*=\eta(g)\,(u_{\delta_1(g)}\otimes u_{\delta_2(g)})\), for all \(g\in\Gamma\).

Paper notes the torsion case is more complicated → **Theorem 8.2**.

## Theorem 8.2 (p. 1207–1208) — classification into \(M_1\bar\otimes M_2\)

**Context:** \(M_i = B_i\rtimes\Gamma_i\) Bernoulli, \(M=M_1\bar\otimes M_2\), \(\Gamma=\Gamma_1\times\Gamma_2\) ICC.  
Source: \(N=D\rtimes_\rho\Lambda\) with infinite almost normal \(\Lambda_0\le\Lambda\) relative property (T).  
Map: \(\theta:N\to M\) a *-homomorphism.

**Hypotheses (must hold):**
1. \(\theta(L(\Lambda_0))\nprec_M L(\Gamma_1)\otimes 1\) and \(\theta(L(\Lambda_0))\nprec_M 1\otimes L(\Gamma_2)\).  
2. \(\theta(N)\nprec_M L(\Gamma_1)\bar\otimes M_2\) and \(\theta(N)\nprec_M M_1\bar\otimes L(\Gamma_2)\).

**Conclusion (torsion-free case, summary):** unital + character + group hom \(\delta:\Lambda\to\Gamma\) + unitary conjugacy form (standard rigid case).  
General torsion case: finite-index / finite-kernel technical form (a)(b).

## Corollary / intertwining (Thm 1.3.1 ≈ Popa Cor 2.3)

Popa intertwining: \(Q\prec_M B\) iff corner embedding / Fourier coefficient lower bound conditions (Thm 1.3.1 citing [33] Thm 2.1 and Cor 2.3).

## Audit consequence (see S006 memo)

Nielsen’s twisted comultiplication \(\Theta(f u_g)=f u_g\otimes\Phi(u_g)\) into \(A_G\bar\otimes A_H\) has, by construction,
\[
\Theta(A_G)\subseteq A_G\bar\otimes L(H)=M_1\bar\otimes L(\Gamma_2)
\]
(when \(M_1=A_G\), \(M_2=A_H\), \(\Gamma_2=H\)).  
This **negates** hypothesis (2) of Theorem 8.2 (second conjunct). Therefore Case-(III)/rigid-output hypotheses of Thm 8.2 are **not met** for this \(\Theta\).
