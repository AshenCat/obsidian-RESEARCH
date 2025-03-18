# Ownership

C, C++ -> Memory Management Control Issue

Garbage Collector solved this issue, but created a new issue. If you want to clean up the memory, it will stop the program and then proceeds to run the rest of the program.

OWNERSHIP was introduced by rust to solve memory safety issues and high performance at the same time

every value has an owner
# Ownership Rules
1. Each value in Rust has a variable that's its owner.
2. There can be only one owner at a time.
3. When the owner goes out of scope, the value will be dropped