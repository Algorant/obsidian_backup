## Chapter 3 of [[Rust By Practice]]

#### Binding and Mutability

- A variable can only be used if it has been initialized
- Use `mut` to mark a variable as mutable

#### Scope

- The range within the program for which the item is valid (denoted with {} usually)

#### Shadowing

- You can declare a new variable with same name as the previous, and we say the first variable is #shadowed by the second one.

#### Unused Variables

- You can add `_` to the front of a variable to make it ok to be unused. 
- You can also add `#[allow(unused_variables)]` to the top of the file
#### Destructuring

- You can use `let` variable followed by tuple to separate variables.

#### Destructuring Assignments

- You can now use tuple, slice, and struct patterns as left hand side of an assignment


