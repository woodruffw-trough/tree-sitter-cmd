# Script fixtures

The Rust integration test parses each UTF-8 script and rejects `ERROR` or
missing nodes. `contracts.tsv` specifies minimum counts of selected node kinds.
These checks do not verify every field or establish runtime behavior.

`sources.tsv` records fixture origins. Adjacent `.LICENSE` files record each
script's license. The `mre-*.bat` examples use this repository's MIT license.

See [`test/corpus`](../corpus/) for expected syntax trees and
[`tests`](../../tests/) for source-range, recovery, and incremental parsing checks.
