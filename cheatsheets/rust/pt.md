---
locale: pt
status: published
title: "Rust"
slug: rust
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de Rust."
tags:
  - rust
  - cheatsheet
  - quick-reference
references:
  - label: "The Rust Programming Language"
    url: https://doc.rust-lang.org/book/
  - label: "The Rust Reference"
    url: https://doc.rust-lang.org/reference/
  - label: "The Cargo Book"
    url: https://doc.rust-lang.org/cargo/
---

# Rust

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Toolchain

**`rustc`, Cargo e Rustup**

```rust
// Typical workflow:
// rustup update stable
// cargo new app
// cargo check
// cargo test
// cargo run
// cargo build --release
```

**Crates, Packages e Targets**

```rust
// Cargo.toml
[package]
name = "example"
version = "0.1.0"
edition = "2024"

[dependencies]
serde = "1"
```

**Expressões, Statements e Blocos**

```rust
fn square(x: i32) -> i32 {
    let result = {
        let y = x * x;
        y
    };

    result
}
```

## Bindings e Tipos

**`let`, `mut` e Shadowing**

```rust
let count = 10;
let mut total = 0;

total += count;

let count = count.to_string();
```

**Tipos Escalares e Compostos**

```rust
let age: u32 = 42;
let ratio: f64 = 0.75;
let ready: bool = true;
let letter: char = '🦀';

let pair: (i32, &str) = (7, "days");
let values: [i32; 3] = [1, 2, 3];
```

**Funções e Tipos de Retorno**

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}

fn log(message: &str) {
    println!("{message}");
}
```

**Type Aliases e Newtypes**

```rust
type UserIdText = String;

struct UserId(String);

fn load_user(id: UserId) {
    // ...
}
```

**Conversões e Casts com `as`**

```rust
let small: u8 = 200;
let wide: u32 = u32::from(small);

let truncated = 300_u16 as u8;
let parsed: u32 = "42".parse()?;
```

## Ownership e Borrowing

**Ownership, Moves e `Copy`**

```rust
let first = String::from("hello");
let second = first;

// println!("{first}"); // moved
println!("{second}");

let a = 10;
let b = a; // i32 implements Copy
println!("{a} {b}");
```

**References e Borrowing**

```rust
fn length(text: &String) -> usize {
    text.len()
}

let name = String::from("Mina");
let size = length(&name);

println!("{name} {size}");
```

**Borrowing Mutável**

```rust
fn append_exclamation(text: &mut String) {
    text.push('!');
}

let mut message = String::from("hello");
append_exclamation(&mut message);
```

**Slices**

```rust
fn first_word(text: &str) -> &str {
    text.split_whitespace()
        .next()
        .unwrap_or("")
}

let values = [10, 20, 30, 40];
let middle: &[i32] = &values[1..3];
```

**Relações de Lifetime**

```rust
fn longer<'a>(a: &'a str, b: &'a str) -> &'a str {
    if a.len() >= b.len() { a } else { b }
}
```

**Dangling References e Borrow Checker**

```rust
fn valid() -> String {
    let text = String::from("owned");
    text
}

// Returning &text here would be rejected.
```

## Fluxo de Controle e Patterns

**`if`, `loop`, `while` e `for`**

```rust
let label = if ready { "ready" } else { "waiting" };

for value in values {
    println!("{value}");
}

let result = loop {
    if done() {
        break 42;
    }
};
```

**Pattern Matching com `match`**

```rust
match status {
    Status::Ready => start(),
    Status::Failed(code) if code >= 500 => retry(),
    Status::Failed(code) => log_error(code),
    Status::Pending => wait(),
}
```

**`if let`, `while let` e `let...else`**

```rust
let Some(user) = find_user(id) else {
    return Err(Error::NotFound);
};

if let Some(email) = user.email.as_deref() {
    println!("{email}");
}
```

**Destructuring e Pattern Bindings**

```rust
struct Point {
    x: i32,
    y: i32,
}

let point = Point { x: 3, y: 4 };
let Point { x, y } = point;

let (first, .., last) = (1, 2, 3, 4);
```

## Structs, Enums e Methods

**Structs e Tuple Structs**

```rust
struct User {
    id: u64,
    name: String,
}

struct UserId(u64);

let user = User {
    id: 42,
    name: String::from("Mina"),
};
```

**Methods e Associated Functions**

```rust
impl User {
    fn new(id: u64, name: impl Into<String>) -> Self {
        Self {
            id,
            name: name.into(),
        }
    }

    fn name(&self) -> &str {
        &self.name
    }
}
```

**Enums e Variants com Dados**

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    Color(u8, u8, u8),
}
```

**`Option<T>` em vez de Null**

```rust
fn find_user(id: u64) -> Option<User> {
    users()
        .into_iter()
        .find(|user| user.id == id)
}

if let Some(user) = find_user(42) {
    println!("{}", user.name);
}
```

## Collections e Strings

**`Vec<T>`**

```rust
let mut values = Vec::with_capacity(4);
values.push(10);
values.push(20);

for value in &values {
    println!("{value}");
}
```

**`String` e `str`**

```rust
let mut owned = String::from("Olá");
owned.push_str(", Rust");

let borrowed: &str = &owned;
println!("{borrowed}");
```

**`HashMap` e Entry API**

```rust
use std::collections::HashMap;

let mut counts = HashMap::new();

for word in ["rust", "go", "rust"] {
    *counts.entry(word).or_insert(0) += 1;
}
```

**Borrowing vs Consuming em Coleções**

```rust
let values = vec![1, 2, 3];

for value in &values {
    println!("{value}");
}

for value in values {
    println!("{value}");
}

// values moved by the second loop
```

## Erros e Results

**`Result<T, E>`**

```rust
fn read_config(path: &str) -> Result<String, std::io::Error> {
    std::fs::read_to_string(path)
}

match read_config("config.toml") {
    Ok(text) => println!("{text}"),
    Err(err) => eprintln!("{err}"),
}
```

**Operador `?`**

```rust
fn load(path: &str) -> Result<String, std::io::Error> {
    let text = std::fs::read_to_string(path)?;
    Ok(text)
}
```

**`panic!` e Erros Irrecuperáveis**

```rust
fn positive(value: i32) -> i32 {
    assert!(value > 0, "value must be positive");
    value
}
```

**Tipos de Erro Customizados**

```rust
#[derive(Debug)]
enum ConfigError {
    Io(std::io::Error),
    InvalidSyntax { line: usize },
}
```

## Traits, Generics e Lifetimes

**Traits e Implementações**

```rust
trait Summary {
    fn summary(&self) -> String;
}

struct Article {
    title: String,
}

impl Summary for Article {
    fn summary(&self) -> String {
        self.title.clone()
    }
}
```

**Funções Genéricas e Trait Bounds**

```rust
fn largest<T>(items: &[T]) -> Option<&T>
where
    T: Ord,
{
    items.iter().max()
}
```

**`impl Trait` e Trait Objects**

```rust
fn make_iter(values: &[i32])
    -> impl Iterator<Item = &i32>
{
    values.iter()
}

fn render(item: &dyn Summary) {
    println!("{}", item.summary());
}
```

**Parâmetros de Lifetime em Tipos e Traits**

```rust
struct Excerpt<'a> {
    text: &'a str,
}

impl<'a> Excerpt<'a> {
    fn text(&self) -> &'a str {
        self.text
    }
}
```

**Associated Types e GATs**

```rust
trait Container {
    type Item;

    fn get(&self) -> Option<&Self::Item>;
}

trait LendingIterator {
    type Item<'a>
    where
        Self: 'a;

    fn next<'a>(&'a mut self) -> Option<Self::Item<'a>>;
}
```

## Closures e Iterators

**Closures e Modos de Capture**

```rust
let prefix = String::from("user:");

let label = |id: u64| {
    format!("{prefix}{id}")
};

println!("{}", label(42));
```

**Trait `Iterator` e Avaliação Lazy**

```rust
let values = vec![1, 2, 3, 4];

let doubled: Vec<_> = values
    .iter()
    .map(|value| value * 2)
    .collect();
```

**`IntoIterator` e Ownership da Iteração**

```rust
let values = vec![1, 2, 3];

for item in &values {
    println!("{item}");
}

for item in values {
    println!("{item}");
}
```

**`collect`, `fold` e Consumers com Short-circuit**

```rust
let sum: i32 = values.iter().copied().sum();

let parsed: Result<Vec<u32>, _> =
    inputs.iter()
        .map(|text| text.parse::<u32>())
        .collect();
```

## Smart Pointers e Interior Mutability

**`Box<T>`**

```rust
enum List {
    Cons(i32, Box<List>),
    Nil,
}
```

**`Rc`, `Arc` e `Weak`**

```rust
use std::sync::{Arc, Weak};

let owner = Arc::new(String::from("shared"));
let another = Arc::clone(&owner);
let weak: Weak<String> = Arc::downgrade(&owner);
```

**`Cell` e `RefCell`**

```rust
use std::cell::RefCell;

let value = RefCell::new(vec![1, 2, 3]);

value.borrow_mut().push(4);

println!("{:?}", value.borrow());
```

**`Deref` e `Drop`**

```rust
struct Guard {
    name: String,
}

impl Drop for Guard {
    fn drop(&mut self) {
        println!("releasing {}", self.name);
    }
}
```

## Modules, Crates e Cargo

**Modules, `use` e Visibility**

```rust
pub mod api {
    pub fn run() {}

    fn internal() {}
}

use crate::api::run;
```

**Dependencies, Features e `Cargo.toml`**

```rust
[dependencies]
serde = { version = "1", features = ["derive"] }

[features]
default = []
json = ["dep:serde_json"]
```

**Cargo Workspaces**

```rust
[workspace]
members = [
    "crates/core",
    "crates/cli",
    "crates/web",
]
resolver = "3"
```

**Documentação e Doctests**

```rust
/// Adds two integers.
///
/// # Examples
///
/// ```
/// assert_eq!(example::add(2, 3), 5);
/// ```
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

## Concorrência e Async

**Threads e Closures `move`**

```rust
use std::thread;

let data = vec![1, 2, 3];

let handle = thread::spawn(move || {
    println!("{data:?}");
});

handle.join().unwrap();
```

**Channels**

```rust
use std::sync::mpsc;
use std::thread;

let (tx, rx) = mpsc::channel();

thread::spawn(move || {
    tx.send(String::from("done")).unwrap();
});

println!("{}", rx.recv().unwrap());
```

**`Arc`, `Mutex`, `Send` e `Sync`**

```rust
use std::sync::{Arc, Mutex};

let counter = Arc::new(Mutex::new(0));

let shared = Arc::clone(&counter);
let handle = std::thread::spawn(move || {
    *shared.lock().unwrap() += 1;
});

handle.join().unwrap();
```

**`async`, `await` e `Future`**

```rust
async fn load() -> Result<String, Error> {
    let first = fetch_part_one().await?;
    let second = fetch_part_two().await?;
    Ok(format!("{first}{second}"))
}
```

**Pinning e Futures Self-referential**

```rust
use std::pin::Pin;
use std::future::Future;

fn poll_later(
    future: Pin<&mut dyn Future<Output = ()>>
) {
    // an executor may poll this pinned future
}
```

## Unsafe, FFI e Macros

**Unsafe Rust e Safety Invariants**

```rust
unsafe fn read_raw(ptr: *const i32) -> i32 {
    // SAFETY: caller guarantees ptr is valid and aligned.
    unsafe { *ptr }
}
```

**Raw Pointers e Memória Manual**

```rust
let mut value = 42_i32;

let ptr: *mut i32 = &mut value;

unsafe {
    *ptr += 1;
}
```

**FFI e Interop com C**

```rust
use std::ffi::c_int;

unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn absolute(value: i32) -> i32 {
    unsafe { abs(value) }
}
```

**Macros Declarativas**

```rust
macro_rules! vec_of_strings {
    ($($value:expr),* $(,)?) => {
        vec![$($value.to_string()),*]
    };
}

let names = vec_of_strings!("Ada", "Mina");
```

**Procedural Macros e Derives**

```rust
#[derive(Debug, Clone)]
struct User {
    id: u64,
    name: String,
}
```

## Testes, Tooling e Produção

**Unit, Integration e Documentation Tests**

```rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn adds_values() {
        assert_eq!(add(2, 3), 5);
    }
}
```

**`rustfmt`, Clippy e Compiler Lints**

```rust
// Typical checks:
// cargo fmt --check
// cargo clippy --all-targets --all-features -- -D warnings
// cargo test
```

**Benchmarking e Profiling**

```rust
pub fn process(values: &[u64]) -> u64 {
    values.iter().copied().sum()
}
```

**APIs Públicas e SemVer**

```rust
pub struct Client {
    inner: Inner,
}

impl Client {
    pub fn new() -> Self {
        // ...
        todo!()
    }
}
```
