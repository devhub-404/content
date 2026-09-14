# Debug Library, Hooks, and Tracebacks

The `debug` library exposes stack, function, local-variable, upvalue, hook, and traceback facilities that are useful for debuggers, profilers, diagnostics, and advanced tooling. It can also bypass ordinary encapsulation assumptions.

```lua
local function work()
    error("boom")
end

local ok, err = xpcall(work, debug.traceback)

if not ok then
    print(err)
end
```

Do not expose the full debug library to untrusted scripts in a sandbox. For application diagnostics, `debug.traceback` and protected-call handlers often provide enough information without giving scripts unrestricted introspection. Hosts can also install hooks for instruction counting or debugging, but hooks have performance cost.
