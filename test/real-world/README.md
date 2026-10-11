# Script fixtures

These batch scripts test whole-file parsing. The integration test checks UTF-8
input and rejects trees containing `ERROR` or missing nodes. `contracts.tsv`
also specifies minimum counts of selected node kinds. These checks do not
establish runtime behavior or verify every field in a tree.

[`../corpus/`](../corpus/) contains smaller examples with expected syntax trees.
The Rust tests under [`../../tests/`](../../tests/) check source ranges,
control-flow structure, recovery, and incremental parsing.

`sources.tsv` records each fixture's origin. Third-party scripts retain their
upstream licenses, recorded in adjacent `.LICENSE` files. The `mre-*.bat`
fixtures are original examples covered by this repository's MIT license.

The fixture collection uses UTF-8, including ASCII, with LF or CRLF endings.
It does not validate OEM code pages, UTF-16, or mixed encodings.
