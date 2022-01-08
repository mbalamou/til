# Rust

* [Crates.io](https://crates.io) - Public package repository
* [Discord](https://discord.gg/rust-lang) - Official discord server
* [Docs.rs](https://docs.rs/) - Documentation host for crates
* [Documentation > Editions](https://doc.rust-lang.org/edition-guide/editions/index.html)
* [Documentation > Standard Library](https://doc.rust-lang.org/std/index.html)
* [Documentation > Test](https://doc.rust-lang.org/test/index.html)
* [Documentation](https://doc.rust-lang.org/) - Official documentation
* [Forum](https://users.rust-lang.org/) - Official forum
* [Learn Rust With Entirely Too Many Linked Lists](https://rust-unofficial.github.io/too-many-lists/)
* [Official site](https://www.rust-lang.org/)
* [Reddit /r/rust](https://www.reddit.com/r/rust)
* [`##rust` @ irc.libera.chat](https://web.libera.chat/?chan=##rust) - IRC channel
* [rustup](https://rustup.rs/) - Toolchain installer and manager

## Books

* [Programming Rust, 2nd Edition (2021)](https://www.oreilly.com/library/view/programming-rust-2nd/9781492052586/)
* [Rust for Rustaceans (2021)](https://nostarch.com/rust-rustaceans)
* [The Rust Programming Language (2019)](https://doc.rust-lang.org/book/)

Read a local copy of "The Rust Programming Language" book in a web browser with: `rustup doc --book`

## Getting started

* [Documentation > Channels](https://rust-lang.github.io/rustup/concepts/channels.html)

Install system packages
```
apt install cargo rustc

# Update Rust on the stable, beta, or nightly channel
channel=stable
#channel=beta
#channel=beta
rustup update ${channel}
rustup default ${channel}
```

Ensure that `~/.cargo/env`
[is sourced in your environment](https://github.com/andornaut/dotfiles/blob/53bff380386a79c805b7bb8337f7c971b859103e/%24HOME/.bashrc.andornaut#L98).
```
if [[ -f "${HOME}/.cargo/env" ]]; then
    source "${HOME}/.cargo/env"
fi
```

Create a project
```
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

* [cargo-make](https://github.com/sagiegurari/cargo-make) - Task runner and build tool
* [Specifying features](https://doc.rust-lang.org/cargo/reference/specifying-dependencies.html)

## Visual Studio Code

* [CodeLLDB extension](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb) - Debugger
* [Rust extension](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust) - Language support. Conflicts with [Rust-analyzer extension](https://marketplace.visualstudio.com/items?itemName=matklad.rust-analyzer) - Language support (new, experimental).
* [Rust-analyzer extension](https://marketplace.visualstudio.com/items?itemName=matklad.rust-analyzer) - Language support (experimental, but **recommended**). Conflicts with [Rust extension](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust).
* [Tasks](https://code.visualstudio.com/docs/editor/tasks#vscode)

`./.vscode/tasks.json`:
```
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
[crossterm](https://github.com/crossterm-rs/crossterm)|Library for controlling terminals
[cursive](https://github.com/gyscos/Cursive)|Text User Interface (TUI) library. ([Comparison to tui](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[rand](https://github.com/rust-random/rand)|Generate random numbers
[Serde JSON](https://github.com/serde-rs/json)|Serialize and deserialize JSON
[tempfile](https://github.com/Stebalien/tempfile)|Create temporary files or directories
[tui](https://crates.io/crates/tui)|Text User Interface (TUI) library. ([Comparison to cursive](https://github.com/gyscos/cursive/wiki/Cursive-vs-tui%E2%80%90rs)).
[uuid](https://github.com/uuid-rs/uuid)|Generate and parse UUIDs

## Debugging

* [Debugging with GDB](https://blog.logrocket.com/debugging-rust-apps-with-gdb/)
