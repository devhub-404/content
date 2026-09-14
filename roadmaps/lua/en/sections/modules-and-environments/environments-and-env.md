# Environments and `_ENV`

Global-name access in Lua is defined through an environment, represented by the `_ENV` mechanism. Loading a chunk with a custom environment changes which global names that chunk can see and assign, making environments useful for configuration and embedded scripting.

```lua
local env = {
    print = print,
    answer = 42,
}

local fn = assert(load(
    "print(answer)",
    "example",
    "t",
    env
))

fn()
```

An environment is not a complete security sandbox by itself. If it exposes a function that can reach the filesystem, process, debug library, or host internals, the loaded code can use that capability. Design environments by capability and audit every value you expose.
