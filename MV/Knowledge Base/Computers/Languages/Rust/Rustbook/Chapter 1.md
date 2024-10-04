
These are my note on [[Knowledge Base/Computers/Languages/Rust/Rustbook/Chapter 1]] of the [[Rustbook]]


#### 1.1 Installation for OS

This covers installation of #rust. Usually done by running `rustup` on your system in one form  or another. This is also how you can update #rust or update the #cargo package manager. I've done it on multiple systems and it's great.

#### 1.2 Hello World

- This covers a basic #hello-world and `rustc` usage to compile
- `rustc <file>` compiles the program and creates an executable
-  [[Rust]] is different from languages such as [[Python]] in that it compiles before it runs. This is a tradeoff similar to languages such as c and c++.

#### 1.3  Cargo

- [[Cargo]] is the way to manage packages in [[Rust]]
- `cargo new <project name>` creates a new project folder, with various items:
	- a `src` folder with a `main.rs` file in it.
	- a `cargo.toml` file which shows installed packages and dependencies of the project, as well as version number.
- `cargo build` builds the project and creates an executable, as well as a `Cargo.lock` file.
	- a `--release` modifier on this command will add optimizations, but in exchange for added build time.
- `cargo check` will attempt to build but not actually do it, to see if you have any errors.

