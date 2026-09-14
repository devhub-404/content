# Debug Library, Hooks y Tracebacks

La `debug` library expone stack, functions, locals, upvalues, hooks y tracebacks útiles para debugger, profiler y tooling. También puede saltarse assumptions normales de encapsulación.

```lua
local function work()
    error("boom")
end

local ok, err = xpcall(work, debug.traceback)

if not ok then
    print(err)
end
```

No expongas la debug library completa a scripts no confiables. Para diagnostics, `debug.traceback` con protected calls suele ser suficiente. Los hosts también pueden instalar hooks para conteo/debugging, pero tienen coste de performance.
