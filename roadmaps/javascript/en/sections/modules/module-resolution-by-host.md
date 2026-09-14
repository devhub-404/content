# Module Resolution by the Host

ECMAScript defines module syntax and linking semantics, but the host decides how a module specifier maps to source code. Browsers primarily resolve URLs and usually require resolvable relative/absolute specifiers unless an import map changes the mapping. Server runtimes and bundlers add package and file-resolution rules.

```js
import { format } from "./format.js";
import { readFile } from "node:fs/promises";
```

That is why a bare package import may work in one environment and fail in a browser without tooling. File extensions, package exports, CommonJS interoperability, aliases, and conditional resolution are environment concerns around the core module system. Test packages from the same runtime and build configuration that consumers will use.
