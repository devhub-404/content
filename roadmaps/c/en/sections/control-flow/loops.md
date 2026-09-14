# `for`, `while`, and `do` Loops

`for` is convenient when initialization, condition, and update belong together. `while` repeats while a condition remains nonzero, and `do ... while` evaluates the condition after the body, so it always executes at least once.

```c
for (size_t i = 0; i < count; ++i) {
    process(items[i]);
}

while (queue_has_items()) {
    consume_next();
}
```

`break` exits the innermost loop or switch, while `continue` advances to the next loop iteration. Be careful with integer loop bounds, especially mixing signed and unsigned sizes. For array traversal, make the bound come from the actual array length or an explicit count passed with the pointer.
