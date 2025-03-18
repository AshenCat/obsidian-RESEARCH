Shadowing is not the same as marking a variable as mutable

Allows you to redeclare a variable to change its value

```rust
let x = 5;
let x = x + 1;
{
    let x = x * 2;
    println!("The value of x in the inner scope is now {}", x); // 12
}
println!("The value of x is now {}", x); // 6
```

