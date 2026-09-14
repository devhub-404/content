# Debug Library, Hooks e Tracebacks

A `debug` library expõe stack, functions, locals, upvalues, hooks e tracebacks úteis para debugger, profiler e tooling. Ela também consegue contornar assumptions normais de encapsulation.

```lua
local function work()
    error("boom")
end

local ok, err = xpcall(work, debug.traceback)

if not ok then
    print(err)
end
```

Não exponha debug library completa a script não confiável. Para diagnostics, `debug.traceback` com protected calls muitas vezes basta. Hosts também podem instalar hooks para contagem/debugging, mas eles têm custo de performance.
