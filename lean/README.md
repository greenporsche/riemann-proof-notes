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
(`literature/README.md`, V2–V4). Unpacked: 175,187 `.lean` files under
`lean/src/`, about 1.3 GB, toolchain `leanprover/lean4:v4.33.1`.
`lean/src/Main.lean` is byte-identical to the pinned mirror's
(`leanprover-community/riemann-hypothesis` at `40e56bab`).

For new Lean proof-reading studies use community `main` at a recorded commit. On 24 November its head was [`9282d3a1`](https://github.com/leanprover-community/riemann-hypothesis/blob/9282d3a102c4aff0e6026746db2a8990f5d9cddd/src/Main.lean#L43-L47). Follow the proof bodies from the target theorem. Use the archive above to reproduce release-era checks and resolve historical references.

We use the archived release for reading and source searches without a local rebuild. Reading notes go in `lean/`, alongside the git-ignored `archive/` directory.
