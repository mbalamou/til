# Rust

* [Crates.io](https://crates.io) - Public package repository
* [Docs.rs](https://docs.rs/) - Documentation host for crates
* [Official site](https://www.rust-lang.org/)
* [The Rust Programming Language](https://doc.rust-lang.org/book/) (book)

Read a local copy of "The Rust Programming Language" book in a web browser with: `rustup doc --book`

## Getting started

```
apt install cargo rustc

# Use the binary template by default: --bin
cargo new ${project_name}

# Or use the library template: --lib
# cargo new --lib ${library_project_name}

cd ${project_name}
vim Cargo.toml
```

## Managing Rust versions

```
# Update Rust on the stable channel
rustup update stable
```

## Cargo

* [Specifying features](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html)

## Frameworks, libraries and tools

Name | Description
--- | ---
[clap](https://github.com/clap-rs/clap)|Parse command line arguments
[chrono](https://github.com/chronotope/chrono)|Date and time library
[chrono-tz](https://github.com/chronotope/chrono-tz)|Timezone library
[cursive](https://github.com/gyscos/Cursive)|Text User Interface (TUI) library. ([Comparison to tui](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[rand](https://github.com/rust-random/rand)|Generate random numbers
[Serde JSON](https://github.com/serde-rs/json)|Serialize and deserialize JSON
[tempfile](https://github.com/Stebalien/tempfile)|Create temporary files or directories
[tui](https://crates.io/crates/tui)|Text User Interface (TUI) library. ([Comparison to cursive](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[uuid](https://github.com/uuid-rs/uuid)|Generate and parse UUIDs

## Debugging

* [Debugging with GDB](https://blog.logrocket.com/debugging-rust-apps-with-gdb/)
