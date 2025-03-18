arrays, tuples, slices, and strings (slice string)

# Arrays
must be of the same type
### Syntax
```rust
let numbers: [i32;5] = [1,2,3,4,5];
println!("Number Array: {:?}", numbers)

let fruits: [&str;3] = ["apple", "banana"];
println!("Fruits Array: {:?}", fruits)
```

# Tuples
Heterogeneous collection of elements of fixed size

### Syntax
```rust
let human: (&str, i32, bool) =("Alice", 30, false);
println!("Human Tuple: {:?}", human)

let my_mix_tuple = ("Kratos", 23, true, [1,2,3,4,5])
println!("My Mix Tuple: {:?}", my_mix_tuple)
```

# Slices
Heterogeneous collection of elements of unknown size at compile time
```rust
let number_slices: &[i32] = &[1,2,3,4,5]
println!("Number Slices: {:?}", number_slices)

let animal_slices: &[&str] = &["cats", "dogs"]
println!("Number Slices: {:?}", animal_slices)

let book_slices: &[&String] = &[
	&"IT".to_string(),
	&"Harry Potter".to_string(),
	&"ZEN".to_string(),
];
println!("Book Slices: {:?}", book_slices);
```

## Strings Vs String slices (&str)

### Strings [ growable, mutable, owned string type]
- Stored in the heap memory
- owned string
```rust
let mut stone_cold: String = String::from("Hell, ");
println!("Stone Cold Says: {}", stone_cold);
stone_cold.push_str("Yeah!")
```

### String Slice (&str)
- reference to a portion of a string stored somewhere in the code
- not an owned string
- memory efficient - do not need to copy the string
- can only reference with data in the same scope

```rust
let string: String = String::from("hello, World!");
let slice: &str = &string[0..5];

println!("Slice Value: {}", slice);
```