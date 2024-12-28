# rs-conllu

This project aims to provide a parser for the CoNLL-U format of the Universal Dependencies project: https://universaldependencies.org/format.html.

## Basic Usage

Parse a file in CoNLL-U format and iterate over the containing sentences.

```rust
let file = File::open("example.conllu").unwrap();

let doc = parse_file(file);

for sentence in doc {
    for token in sentence.unwrap() {
        println!("{}", token.form);
    }
}
```

## Features

- Tested on version 2.11 UD treebanks
- Handles different types of token ids (single, range, empty)

## Limitations

Parsing happens in a "flat" manner, relations between tokens are not respected.
