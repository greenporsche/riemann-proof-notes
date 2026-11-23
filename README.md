# Riemann proof notes

I'm teaching myself how Levent Alpöge's proof of the Riemann hypothesis
works. These notes follow the questions I run into, the ideas I learn along
the way, and the parts I can now explain. Each chapter comes with a video.
Together they're meant to add up to a self-created-self-study course on the proof, starting from
high-school math.

## Chapters

Chapters will appear in `writeups/`, one per concept, in the order in which I
learn them. The first is on how knowing which primes divide a number, and how
big it is, bounds the primes. That is the idea the whole proof is built on.

## Where things stand

On 20 November 2026 Alpöge released a formal proof, in the Lean proof
assistant, of the Riemann hypothesis and of the generalised Riemann hypothesis
for Dirichlet L-functions. Independent proof checkers have verified it.
Mathematicians have begun explaining parts of how it works; none of the
explanations is complete yet, and nothing has been refereed.

The details, source by source and dated:
[`literature/state-of-understanding.md`](literature/state-of-understanding.md)
and [`literature/README.md`](literature/README.md).

## What's in this repository

- `literature/`: every source I track, and what each one shows.
- `lean/`: notes on the Lean code, and how to get a copy of it.

The proof and the formal development are Levent Alpöge's
(https://alpo.ge/remark.pdf). The sources quoted here belong to their authors.
