# Windows behavior tests

[`tests/windows_oracle.rs`](../../tests/windows_oracle.rs) runs short batch
scripts through native `cmd.exe`. Its regression tests check observable output
and file effects. Parser tests separately check the corresponding syntax trees.

An optional observation report includes script bytes, output, exit status,
the CST, and recovery nodes. Output is escaped byte for byte, including
undecodable bytes from the active OEM code page.

Successful execution does not establish a particular CST shape. Diagnostics
depend on the system language, and exit status can come from an executed
command rather than the parser.
