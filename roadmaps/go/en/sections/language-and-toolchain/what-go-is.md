# What Go Is

Go is a statically typed, garbage-collected language designed for simple tooling, explicit concurrency, packages, and efficient compiled programs. It favors a small language surface, composition through interfaces, and conventions enforced by tools such as `gofmt` rather than many competing style choices.

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Go")
}
```

The current specification documents language version Go 1.27. Go's compatibility promise makes older source unusually stable, but the language and standard library still evolve. Learn the current language, then recognize older idioms when reading existing code instead of treating historical limitations as present-day rules.
