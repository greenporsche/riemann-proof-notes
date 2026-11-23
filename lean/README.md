# The Lean development

Alpöge's formal proof, as released on 20 November 2026 (https://alpo.ge/remark.pdf).
It is not redistributed here. To get a local copy for reading:

```sh
mkdir -p lean/archive/parts && cd lean/archive/parts
for i in $(seq -w 1 14); do curl -fsSO "https://alpo.ge/lean.tar.gz.part$i"; done
cat lean.tar.gz.part* > ../lean.tar.gz && cd ..
shasum -a 256 lean.tar.gz   # must print 9631b4f020199e580ba86178cb56c6e9b09f690c2369a80dc4334aa93f49c7fc
tar -xzf lean.tar.gz
```

Our copy (fetched 2026-11-23 UTC): 239,275,554 bytes, SHA-256 as above,
matching the hashes published by Rubinstein, Sutherland and Arledge
(`literature/tracker.md`, V2–V4). Unpacked: 175,187 `.lean` files under
`lean/src/`, about 1.3 GB, toolchain `leanprover/lean4:v4.33.1`.
`lean/src/Main.lean` is byte-identical to the pinned mirror's
(`leanprover-community/riemann-hypothesis` at `40e56bab`).

We read and search this copy; we do not rebuild it. Reading notes go in this
folder, next to `archive/` (which git ignores).
