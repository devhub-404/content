# `package.path`, `package.cpath`, and Searchers

The `package` library controls module loading. `package.path` contains patterns for Lua source modules and `package.cpath` for native C modules. Searchers determine how a module name is resolved, and `package.loaded` records loaded modules.

```lua
print(package.path)
print(package.cpath)

local json = require("json")
```

Applications should configure module paths deliberately rather than changing the process working directory and hoping relative paths resolve. Embedded hosts can install custom searchers to load code from archives, assets, databases, or other controlled sources without exposing the entire filesystem.
