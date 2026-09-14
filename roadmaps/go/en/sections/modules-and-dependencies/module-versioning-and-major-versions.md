# Module Versioning and Major Versions

Published Go modules follow semantic versioning conventions, and v2 or later major versions normally include the major version suffix in the module and import path. This lets incompatible major versions coexist in one build graph.

```go
// v1 import:
import "example.com/lib"

// v2+ import:
import "example.com/lib/v2"
```

Do not mutate a previously published version tag. Release a new version for changes and preserve backward compatibility within a major line when possible. Public package paths, exported identifiers, interfaces, and behavior all participate in compatibility.
