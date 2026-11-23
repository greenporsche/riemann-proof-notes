# State of understanding

What is known about the proof as of **2026-11-23 (UTC)**, and what is open.
Every line points to an entry in `tracker.md`.

## In one paragraph

On 20 November 2026 Levent Alpöge, working with Claude, released a formal
proof in Lean of the Riemann hypothesis and of the generalised Riemann
hypothesis for Dirichlet L-functions (A1). Within a day, independent proof
checkers accepted it, and the Lean and Mathlib communities certified that the
theorem proved is exactly Mathlib's statement of RH (V1–V5). Alpöge released
the Lean formalization, not a written proof (A1). The explanations tracked here
(E1–E4) cover parts of the argument, including a reduction of the main
inequality to stated inputs (E1), and each says how far it goes. The Clay
Institute still lists the problem as unsolved (O1), and none of the material
tracked here has been refereed.

## Done

| What | How we know |
|---|---|
| The formal proof compiles; Lean replayed every compiled module; nanoda and con-leche accepted the full export; con-leche and con-ron matched all five statements | V1, V2, V3, V4 |
| It uses only Lean's three standard axioms | V2, V3, V4 |
| The proved theorem is Mathlib's `RiemannHypothesis`, and that statement has been vetted as the classical one | V1, V3 |
| Scope: RH and GRH for Dirichlet L-functions only | V2, E2 |
| The last steps are classical: a zero-free half-plane Re s > ½, carried to the critical line by the functional equation | E2 Thm 1.2, E4 |
| The shape of the argument: one-sided bounds of size x^(½+ε), for every ε > 0, on a smoothed sum over prime powers, valid throughout windows [Y, Y^(3/2)] with arbitrarily large Y, exclude zeros to the right of the critical line | E1 abstract, E2 abstract, E4 |
| The engine: Chebyshev's "divisibility against size" idea, run on lattices built from chains of about √x theta lifts, with the √x balancing two errors | E1 §I.0 steps 2–7, A1, E3 abstract |
| The divisibility and size calculations illustrated by a worked lemniscate example (outside the proof) | E1 v2 §III.12 |

## Open

| What | Where it is discussed |
|---|---|
| A human-readable proof of the main inequality (M) | E1: reduced to 13 hypotheses, none proved outright; §I.12 lists what remains |
| The forced divisibility of theta-lift periods at inert primes, "the mathematical heart of the method" | E3 §6 item 1; E1 step 3 (hypothesis (B)) |
| Sharpness of the slope inequality; a uniform Selmer bound; arithmetic proportionality; statements named stronger than they are; in-source proofs of major theorems | E3 §6 items 2–6 |
| Matching the 195 entries the development takes as published results to the literature | E1 §III.13 (matches proposed "from memory") |
| Shorter proofs | A1 expects them; none in the material tracked here |
| Refereed publication; Clay's assessment | none in the material tracked here; O1 |
