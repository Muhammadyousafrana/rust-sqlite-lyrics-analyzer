# Rust SQLite Lyrics Analyzer

A small Rust project that reads a lyrics dataset from a text file, stores it in an SQLite database, and computes word-frequency statistics.

This repository is currently named `Rust-Zero-Shot-Classification`, but the actual implementation does not perform zero-shot classification. Instead, it demonstrates:

- reading text data from a local file
- inserting records into SQLite with `rusqlite`
- analyzing word frequency in the corpus
- printing the most common terms from the lyrics

## Why the current name is misleading

The code in this repo uses `rusqlite` and a local `lyrics.txt` file, and the public functions are `read_lyrics`, `create_db`, `analyze_lyrics`, and `print_word_freq`. There is no zero-shot classification model, transformer pipeline, or label-based inference in the current implementation.

## Recommended project name

The most accurate and clear name would be:

- `rust-sqlite-lyrics-analyzer`

Alternative naming options:

- `rust-lyrics-analyzer`
- `rust-lyrics-frequency-analyzer`
- `rust-sqlite-wordfreq`

## Project structure

```text
Rust-Zero-Shot-Classification/
├── LICENSE
├── README.md
├── sqlite_hf/
│   ├── Cargo.toml
│   ├── Makefile
│   ├── lyrics.db
│   └── src/
│       ├── lib.rs
│       ├── lyrics.txt
│       └── main.rs
└── .gitignore
```

## Features

- Reads lyrics from `sqlite_hf/src/lyrics.txt`
- Creates or updates a SQLite database at `sqlite_hf/lyrics.db`
- Stores each lyric line as a row in the `lyrics` table
- Counts word frequency across the dataset
- Prints the most frequent words to the console

## Tech stack

- Rust
- `rusqlite`
- `rust-bert` (listed in `Cargo.toml`, though the current implementation does not actually use it)
- `clap`

## Setup

From the repository root:

```bash
cd sqlite_hf
cargo build
cargo run
```

## Notes

The code currently hardcodes the lyrics file path:

```rust
Path::new("/workspaces/Rust-Zero-Shot-Classification/sqlite_hf/src/lyrics.txt")
```

If you run this project outside the original workspace layout, update that path in `sqlite_hf/src/lib.rs` to match your local environment.

## Example output

```text
the: 12
and: 9
you: 8
love: 7
...
```

## License

This project is licensed under the MIT License.
