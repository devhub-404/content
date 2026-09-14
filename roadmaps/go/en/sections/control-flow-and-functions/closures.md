# Function Values and Closures

Functions are first-class values and can be stored, passed, and returned. A closure captures variables from its surrounding lexical environment, and the captured variables remain alive as long as the closure needs them.

```go
func makeCounter() func() int {
    count := 0

    return func() int {
        count++
        return count
    }
}
```

Closures are common in HTTP handlers, callbacks, sort predicates, middleware, and goroutines. Be deliberate about captured mutable state, especially when closures run concurrently. A closure that captures a large object can also extend that object's lifetime.
