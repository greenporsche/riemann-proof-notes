# Literature tracker: Alpöge's proof of the Riemann hypothesis

One entry per source, newest at the top within each section. Each entry says
what the source shows, what it says it does **not** show, and how much of it
we have read. Captured copies are kept locally in `sources/` and are not
redistributed in this repository; `sources/SHA256SUMS` identifies each one,
and `sources/ACCESSED.txt` gives the capture times (first: 2026-11-23 07:48 UTC).

Status words used here:
- **machine-checked**: a proof checker accepted the formal proof;
- **explained**: a human-readable account exists, saying how far it goes;
- **refereed**: accepted by a journal after peer review. Nothing below is refereed yet.

Last updated: 2026-11-24 (UTC).

On 24 November the release archive, both Waterloo drafts and four other PDFs were compared again with their published versions, and all matched.

## The announcement

### A1. Alpöge, remark (4 pp.), 20 Nov 2026
- **Link:** https://alpo.ge/remark.pdf · copy: `sources/alpoge-remark/remark.pdf`
  (SHA-256 `3fc97784…eb8d`, matches the hash in Arledge's receipts, V4).
- **Shows:** the announcement. "I believe I have, working with Claude, discovered
  a proof of the Riemann Hypothesis." The method "extends much further,
  resolving the so-called Generalized Riemann Hypothesis". The formal proof is
  a 14-part Lean archive (alpo.ge/lean.tar.gz.part01–14). Gives a dated
  timeline of 20 steps (6 Oct to 16 Nov 2026) that Claude compiled.
- **Says it does not show:** a human-readable proof. "I am presenting the world
  with a complete argument before having mastered a massive neighbourhood
  around its mathematics … I decided to only present Lean." A generated write-up
  of "250,000+ pages" exists but was not released. Expects "short arguments to
  follow fairly quickly".
- **Read:** in full.

## Verification of the formal proof (machine checks)

### V1. Lean FRO and Mathlib Initiative, joint statement, 21 Nov 2026 13:55
- **Link:** https://leanprover-community.github.io/blog/posts/riemann-hypothesis/
  · copy: `sources/lean-mathlib-statement/post.html`
- **Shows:** "We hereby certify that both the statement and the proof of the
  Riemann Hypothesis are correct." Four criteria: the statement is Mathlib's
  `RiemannHypothesis`, "carefully vetted by experts in Lean and number theory";
  the library compiles; two tools (`comparator`, `con-leche --compare`) confirm
  that the proved theorem is exactly Mathlib's statement; the export was checked
  by several kernels, including Lean's and con-leche/con-ron. The statement
  attributes the set-theoretic soundness proofs to con-leche and con-ron: they
  "come with a formal proof, relative to set theory, that they cannot accept a
  false proof".
  The updated byline names the Lean FRO and the Mathlib Initiative as joint authors.
- **Says it does not show:** anything about human understanding. It "look[s]
  forward to all the activity in the mathematical community that will help
  explain the new ideas in this proof."
- **Read:** in full.

### V2. Sutherland (MIT), verification log, updated 24 Nov 2026 05:25 UTC
- **Link:** https://math.mit.edu/~drew/grh/ · copy: `sources/sutherland-log/index.html`
- **Shows:** checks "run with Claude Code". For the main proof: all 175,187
  modules compile; `#print axioms` gives only `propext`, `Classical.choice`,
  `Quot.sound`; Lean replayed every compiled module (`leanchecker`); two
  independently written kernels, nanoda and con-leche, "accept the full exported
  proof"; con-leche and con-ron matched all five theorems against the
  statements; lean4lean accepted every compiled module; an independent sandboxed
  rebuild reproduced the export byte for byte.
- **24 November update:** Lean’s default and paranoid kernels accepted the full original export. Standalone Comparator v4.33.0 passed against the archive’s challenge using the original build files. The separate v4.36.0 run with the canonical challenge had passed its paranoid and nanoda stages. Its default-kernel stage was still running.
- Also documents a harmless non-determinism in one compiled module (a
  bound-variable name, Lean issue #15498).
- **Scope:** RH and GRH for Dirichlet L-functions (five theorems). "Dedekind zeta
  functions, Hecke L-functions and automorphic L-functions in general are not
  among the statements that were checked."
- **Read:** status table and scope note.

### V3. Rubinstein (Waterloo), independent Lean check, complete 21 Nov 2026 10:10 UTC
- **Link:** https://mrubinst.github.io/grh-lean-verification/ · copy:
  `sources/rubinstein/grh-lean-verification.html`
- **Shows:** run with Claude Code on University of Waterloo servers. Archive
  downloaded twice and hash-checked (`lean.tar.gz`, 239,275,554 bytes); theorem
  statements read by hand; Lean v4.33.1 and Mathlib pinned to upstream commits;
  a static scan for `sorry`, `axiom`, `native_decide` and the like found none;
  full compile; axioms; kernel replay; the independent Rust kernel nanoda
  checked 1,484,729 declarations with no errors.
- **Read:** status and checklist.

### V4. Arledge, independent verification receipts (GitHub)
- **Link:** https://github.com/Infatoshi/rh-verification-receipts · copy:
  `sources/arledge/README.md`
- **Shows:** an independent rebuild (finished 20 Nov 2026 19:05 UTC), a
  statement pin, an axiom audit and a nanoda check (1,484,729 declarations, 0
  errors). The source archive's SHA-256 matches Sutherland's.
- **Read:** README summary.

### V5. Naskręcki, riemann-rev: map, guide and record of checks
- **Link:** https://nasqret.github.io/riemann-rev/ · repo
  https://github.com/nasqret/riemann-rev · copy: `sources/riemann-rev/`
- **Shows:** a status dashboard of "who has checked what". Front page: "Two
  independent kernels accepted the complete proof, and all five theorems matched
  the canonical Mathlib challenge … the mathematics has not yet been refereed."
  It also hosts explanations (E4).
- **Note:** the front page says its record is "as of 2026-11-20 23:51 UTC"
  although we captured it on 23 Nov. Recheck it before citing the dashboard.
- **Read:** front page only.

The Waterloo index on 23 November linked a full kernel replay attributed to
Simon DeDeo (https://photos.proofsandreasons.io/wright/alp-replay.json). The 24 November index omits the link.

## Explanations (human-readable accounts)

### E1. Rubinstein et al., "The Alpöge–Claude proof of the Riemann hypothesis explained for the Riemann zeta function"
- **v2:** 265 pp., working draft, 22 Nov 2026 · **v1:** 164 pp., 21 Nov 2026.
- **Link:** https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/ ·
  copies: `sources/rubinstein/zeta-paper_v{1,2}.pdf` (+ `.txt` extracts).
- **Authors as printed:** "Claude Fable 5.2, Codex Astra 6.2, and Gemini Carbon
  at the behest of Michael O. Rubinstein".
- **Shows:** the proof specialised to ζ, "in the style of classical analytic
  number theory". The strategy in eight steps, starting from Chebyshev's and
  Erdős's bound on primes from the middle binomial coefficient: "The proof …
  described here is Chebyshev's argument, run with a far better 'integer'."
  Deduces RH from one main inequality (M) plus two estimates for Dirichlet
  characters, and proves the two estimates from cited theorems. v2 illustrates
  the divisibility and size calculations with a worked lemniscate example (an
  illustration outside the proof), and adds a census of 195 entries the Lean
  development gathers under the heading of published results, "including
  repetitions and one unused slot".
- **Says it does not show:** "(M) itself is not proved here." Part III reduces
  (M) to thirteen numbered hypotheses: "None of the thirteen hypotheses is proved
  outright here." §I.12
  lists what remains to be written up: the construction, divisibility, size,
  levels/counts/covolumes/slopes, rank, and more. "The bibliographic attributions
  proposed in the census (§III.13) are from memory."
- **Read:** front matter, §I.0 (steps 1–7), §I.12.

### E2. Slijepčević, "Outline of Alpöge's proof of the generalised Riemann hypothesis", hexagon:2611.00812v1, 94 pp., 21 Nov 2026
- **Link:** https://hexagonmath.org/pdf/2611.00812 · copy:
  `sources/slijepcevic-outline/hexagon-2611.00812v1.pdf` (+ `.txt`).
- **Shows:** the path of the proof of the main theorem (L(s, χ) ≠ 0 for
  Re s > ½, except at the pole s = 1 of a principal character), "as far as we
  understand it". Each numbered statement is "compared with it clause by
  clause". Prepared "with the help of Aleph, an
  AI math research assistant". Theorem 1.2 deduces RH from the zero-free
  half-plane by the functional equation.
- **Says it does not show:** "We have not verified it. The development is very
  large, and we have read only part of it." It also says "what we do not yet
  understand".
- **Read:** abstract, §1.1–1.2.

### E3. Pei, "A roadmap of the claimed Lean proof of the Riemann hypothesis and GRH for Dirichlet L-functions", 23 pp., Nov 2026
- **Link:** https://peabrane.github.io/files/pei-2026-claimed-lean-proof-rh-roadmap.pdf
  · doi:10.5281/zenodo.24405360 · copy: `sources/pei-guide/pei-2026-roadmap.pdf` (+ `.txt`).
- **Shows:** a reading guide built from the development's definitions and
  statements and from A1. By folder, "about 81% of the development's 17.4 million
  lines is formalized standard background and about 5% holds the core
  bookkeeping". Reads the argument as "Stepanov's auxiliary-polynomial method
  transplanted from function fields to Z". §6 "Where to look first" lists six
  places where "the weight of the argument rests", stating "They are not findings
  of error". §7 gives a separate reading plan for human readers.
- **Says it does not show:** "we did not build the development, and we make no
  claim that the proof is correct." Written when "no independent check of it
  had been reported".
- **Read:** abstract, contents, §6.

### E4. Naskręcki (riemann-rev), "The proof of the Riemann hypothesis announced by L. Alpöge: its architecture", 11 pp.
- **Link:** https://nasqret.github.io/riemann-rev/guide/proof-guide.pdf · copy:
  `sources/riemann-rev/proof-guide.pdf` (+ `.txt`).
- **Shows:** "One hard estimate and two classical transformations of it": a
  square-root upper bound on a smoothed prime sum, on sparse long intervals; a
  localised Landau theorem turning it into a zero-free half-plane; functional
  equations carrying that to the critical line. A flow diagram marks which
  implications are machine-checked. The site also has three "deformalization"
  notes that rewrite clusters of the Lean code as ordinary mathematics with full
  proofs, an atlas, a blueprint and a "book".
- **24 November addition:** the [third note](https://nasqret.github.io/riemann-rev/digests/layer-descent.pdf) treats descent to a layer of the cyclotomic tower and includes a concordance to 70 Lean declarations.
- **Read:** first page of the architecture guide and the updated index.

## Official status

### O1. Clay Mathematics Institute, Millennium Prize page
- **Link:** https://www.claymath.org/millennium/riemann-hypothesis/ · copy: `sources/clay/riemann-hypothesis.html`
- **Page label:** “Unsolved” in the 23 November capture and “Active” on 24 November. The page gives no prize decision.

## The formal proof itself

- Archive: alpo.ge/lean.tar.gz.part01–14, assembled 239,275,554 bytes, SHA-256
  `9631b4f0…49c7fc` (V3, V4). Lean v4.33.1, 175,187 files, about 17.4 million
  lines, no comments or docstrings (E3).
- Browsable mirror: https://github.com/leanprover-community/riemann-hypothesis,
  pinned commit `40e56bab026552e089d7afcfeff08d2defb9c005`.
  [`src/Main.lean`](https://github.com/leanprover-community/riemann-hypothesis/blob/40e56bab026552e089d7afcfeff08d2defb9c005/src/Main.lean)
  (12 lines) is captured at `sources/lean-mirror/Main.lean`.
- The 24 November reading pin on community `main` is [`9282d3a1`](https://github.com/leanprover-community/riemann-hypothesis/blob/9282d3a102c4aff0e6026746db2a8990f5d9cddd/src/Main.lean). New studies should record their commit and follow the proof bodies from their target theorem.
- `Main.lean` states five theorems: `riemannHypothesis : RiemannHypothesis`,
  `riemannZeta_eq_zero_re`, `LFunction_ne_zero_of_half_lt_re`,
  `LFunction_eq_zero_re`, `LFunction_eq_zero_re_of_isPrimitive`.

## To read next
- E1 v2 Parts I–II in full (the main explanatory text).
- E4 guide in full; the riemann-rev dashboard and deformalization notes.
- E2 §2 (Propositions 2.3, 2.5).
- The Lean mirror: the RH statement file and the definitions `Main.lean` uses.
- Clay's prize rules (for O1).
- Press: Scientific American, Science, Quanta, Phys.org, Al Jazeera (found
  22 Nov, not yet read beyond search summaries).
