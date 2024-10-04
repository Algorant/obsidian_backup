

#### Instructions
- create empty folder, name it whatever project name
- create a `Cargo.toml` and put this in it
	
```rust
[workspace]
members = [
    "hello"
]

resolver = "2"
```

- `members` is just the projects added when you do `cargo new`, make sure to add `--vcs none` so it doesn't add git stuff
- also delete the `target` folder if it will not be used, takes up space and has [[C]] stuff in it, not [[Rust]]
- 
