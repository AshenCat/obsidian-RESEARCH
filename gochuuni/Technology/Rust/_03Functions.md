a function / variable should be written in snake case
> snake case: hello_world
> kebab case: hello-world
# main function
- Entry point of the rust code
# Hoisting
Rust supports hoisting, meaning functions can be declared at the top or bottom of the file

# Expression vs Statements
Expression evaluates into something of value (Most common would be logical operators && || ! > <)

Statements are lines of code that does not evaluate any value (variable declaration)

```rust
let _X: i32 = {
	let price: i32 = 5;
	let qty: i32 = 10;
	price * qty // notice there's no semi-colon because this is an expression
};
println!("Result is: {}", _X)
```

# Return value

```rust
fn add (a: i32, b: i32) -> i32  {
	a + b
}
```