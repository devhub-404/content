# Go Workspaces

A Go workspace (`go.work`) lets multiple local modules participate in one development build without publishing or adding permanent replace directives to each module. It is useful for coordinated multi-module development.

```go
// go.work
go 1.27

use (
    ./service
    ./library
)
```

A workspace is a developer/build environment construct, not a replacement for each module's independent dependency correctness. Test modules as consumers would use them too, so the workspace does not hide a missing published dependency or incorrect module path.
