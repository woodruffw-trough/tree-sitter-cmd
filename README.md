# tree-sitter-cmd

A [Tree-sitter](https://tree-sitter.github.io/tree-sitter/) grammar for Windows
batch scripts (`.bat` and `.cmd`), intended for static analysis.

## Usage

Only Rust bindings are provided:

```rust
use tree_sitter::Parser;

let mut parser = Parser::new();
parser
    .set_language(&tree_sitter_cmd::LANGUAGE.into())
    .expect("loading cmd grammar");

let tree = parser.parse("@echo off\r\n", None).unwrap();
println!("{}", tree.root_node().to_sexp());
```

To parse a file with the CLI, run these commands from a checkout:

```sh
cargo install --locked --version 0.26.11 tree-sitter-cli
tree-sitter parse path/to/script.bat
```

The generated parser is included in the repository.

## Limitations

The grammar parses source without expanding variables or executing commands.
Runtime expansion can change how `cmd.exe` interprets that source. A tree without
syntax errors does not guarantee that a script will run successfully.

The parser does not detect input encodings. Node byte ranges refer to the
buffer supplied to Tree-sitter.

See the [syntax tree reference](GRAMMAR_DESIGN.md) for node fields, parsing
behavior, error recovery, and unsupported syntax.

## License

[MIT](LICENSE).
