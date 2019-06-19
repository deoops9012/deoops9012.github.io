---
layout: post
title: Getting Started for Rust
author: Paul
date: 2019-6-19
update: 2019-6-19
tags: [languadge, rust, lean, start]
published: false
---

So start to lean `Rust` again🤣. This time notes every steps and knowledge.

This note comes from `https://www.rust-lang.org/learn/get-started`.

## 1. hello world

`cargo new {name of project}` create a new project. It's writen in `Rust`, managed by `Cargo`.

Then we got a `hello world`.

```rust
// main.rs
fn main() {
    println!("Hello, world!");
}
```

`cargo run` will run the code in debug mode. It just print hello world.


## 2. add dependancies

add a line in `Cargo.toml` like this

```
[dependencies]
ferris-says = "0.1"
```

If run `cargo build`, it will search a crate named `ferris-says` on `crates.io`, and download it.

All dependencies store in `~/.cargo`.

```rust
use ferris_says::say;
use std::io::{stdout, BufWriter};

fn main() {
    let stdout = stdout();
    let out = b"Hello fellow Rustaceans!";
    let width = 40;

    let mut writer = BufWriter::new(stdout.lock());
    say(out, width, &mut writer).unwrap();
}
```

next step. Read `rustup docs --book`.