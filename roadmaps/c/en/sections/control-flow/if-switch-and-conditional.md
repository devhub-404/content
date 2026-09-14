# `if`, `switch`, and the Conditional Operator

`if` selects a branch from a scalar condition, while `switch` dispatches on integral or enumeration values using `case` labels. A `switch` case continues into the following case unless control leaves with `break`, `return`, or another jump, so intentional fallthrough should be explicit.

```c
if (score >= 90) {
    grade = 'A';
} else if (score >= 80) {
    grade = 'B';
} else {
    grade = 'C';
}

const char *label = ready ? "ready" : "waiting";
```

The conditional operator `?:` is an expression and is useful when one value depends on a condition. Keep conditions and switch cases focused on domain decisions. Compiler warnings can catch suspicious fallthrough, duplicated conditions, and unreachable cases.
