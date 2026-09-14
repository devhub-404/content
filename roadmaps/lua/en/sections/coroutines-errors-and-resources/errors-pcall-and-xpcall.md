# Errors, `pcall`, and `xpcall`

Lua raises errors with `error`. A protected call with `pcall` catches an error and returns a success boolean followed by either normal results or the error object. `xpcall` additionally lets you run a message handler, commonly to attach traceback information.

```lua
local function parse()
    error("invalid input")
end

local ok, err = pcall(parse)

if not ok then
    print("failed:", err)
end
```

Use protected calls at boundaries where recovery or isolation is meaningful, such as plugin execution or request processing. Do not wrap every small function in `pcall` merely to suppress failures. Preserve enough context to diagnose the original problem, and decide which layer owns logging or user-facing reporting.
