# Packages and Imports

Every Go source file belongs to a package, and packages are the unit of compilation and namespace organization. Files in the same package contribute to one package scope, while imports make exported identifiers from other packages available through their package name.

```go
package report

import (
    "fmt"
    "time"
)

func PrintNow() {
    fmt.Println(time.Now())
}
```

A package name should describe one coherent responsibility. Import cycles are forbidden, which pushes designs toward directed dependency graphs. Keep package APIs small and avoid generic buckets such as `util` when the functions actually belong to clearer domain packages.
