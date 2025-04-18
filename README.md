# redev

[![Crate](https://img.shields.io/crates/v/redev.svg)](https://crates.io/crates/redev)
[![API](https://docs.rs/redev/badge.svg)](https://docs.rs/redev)

Cross-platform simulation and global listening for keyboard and mouse input.

## Listening for input

The `listen` and `grab` [^1] functions can be used to run a callback for all input events.

```rust
redev::listen(|e| dbg!(e))?;
```

## Simulating input

The `simulate` function can be used to send input events.

```rust
use redev::{simulate, EventType, Key};

simulate(&EventType::KeyPress(Key::KeyS))?;
```

## Serialization

Serde support is gated behind the `serde` feature.

## Acknowledgements

- This crate is a fork of a fork of a fork of [Narsil's `rdev`
  crate](https://crates.io/crates/rdev), created to ensure continued maintenance and to make
  Rustdesk's many useful additions available on crates.io.
- [Enigo](https://github.com/Enigo-rs/Enigo), an input simulation library, served as inspiration and reference for Narsil's original crate.

[^1]: Not available on Linux
