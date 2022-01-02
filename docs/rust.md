# Rust

* [Crates.io](https://crates.io) - Public package repository
* [Discord](https://discord.gg/rust-lang) - Official discord server
* [Docs.rs](https://docs.rs/) - Documentation host for crates
* [Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)
* [Forum](https://users.rust-lang.org/) - Official forum
* [Official site](https://www.rust-lang.org/)
* [Reddit /r/rust](https://www.reddit.com/r/rust)
* [`##rust` @ irc.libera.chat](https://web.libera.chat/?chan=##rust) - IRC channel
* [rustup](https://rustup.rs/) - Toolchain installer and manager
* [The Rust Programming Language](https://doc.rust-lang.org/book/) - Official book

Read a local copy of "The Rust Programming Language" book in a web browser with: `rustup doc --book`

## Getting started

```
apt install cargo rustc

# Update Rust on the stable channel
rustup update stable

# Use the binary template by default: --bin
cargo new ${project_name}

# Or use the library template: --lib
# cargo new --lib ${library_project_name}

cd ${project_name}
vim Cargo.toml

cargo build
cargo run
```

## Cargo

* [Specifying features](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html)

## Visual Studio Code

* [Tasks](https://code.visualstudio.com/docs/editor/tasks#vscode)

```
# ./.vscode/tasks.json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "cargo build",
      "type": "shell",
      "command": "cargo build",
      "args": [],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    },
    {
      "label": "cargo run",
      "type": "shell",
      "command": "cargo",
      "args": [
        "run"
      ],
      "group": {
        "kind": "test",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```

## Frameworks, libraries and tools

Name | Description
--- | ---
[anyhow](https://github.com/dtolnay/anyhow)|Concrete `Error` type built on `std::error::Error`
[clap](https://github.com/clap-rs/clap)|Parse command line arguments
[chrono](https://github.com/chronotope/chrono)|Date and time library
[chrono-tz](https://github.com/chronotope/chrono-tz)|Timezone library
[cursive](https://github.com/gyscos/Cursive)|Text User Interface (TUI) library. ([Comparison to tui](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[rand](https://github.com/rust-random/rand)|Generate random numbers
[Serde JSON](https://github.com/serde-rs/json)|Serialize and deserialize JSON
[tempfile](https://github.com/Stebalien/tempfile)|Create temporary files or directories
[termion](https://gitlab.redox-os.org/redox-os/termion)|Library for controlling TTYs
[tui](https://crates.io/crates/tui)|Text User Interface (TUI) library. ([Comparison to cursive](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[uuid](https://github.com/uuid-rs/uuid)|Generate and parse UUIDs

## Debugging

* [Debugging with GDB](https://blog.logrocket.com/debugging-rust-apps-with-gdb/)
