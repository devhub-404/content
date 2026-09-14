# `load`, `loadfile`, and Dynamic Chunks

`load` compiles a chunk from text or a reader function and returns a callable function when compilation succeeds. `loadfile` performs the same job from a file. Compilation failure is reported as a result instead of automatically executing anything.

```lua
local fn, err = load("return 20 + 22")

if not fn then
    error(err)
end

print(fn())
```

Dynamic loading is useful for configuration languages, plugins, generated code, and embedding, but loading untrusted text as Lua code grants the capabilities available in its environment. Prefer data formats when you only need data, and use a deliberately restricted environment when executable configuration is truly required.
