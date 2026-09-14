# Local Functions and Recursion

Functions can be nested to keep helpers local to one algorithm, and closures can capture variables from their surrounding scope. The `tailrec` modifier asks the compiler to optimize eligible tail-recursive functions into loops.

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

Use recursion when it mirrors the problem structure and depth is controlled. Tail recursion is not a general guarantee for every recursive call shape, so large recursive traversals may still need an explicit stack or iterative algorithm.
