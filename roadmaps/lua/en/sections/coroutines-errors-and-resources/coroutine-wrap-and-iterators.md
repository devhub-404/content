# `coroutine.wrap` and Coroutine-based Iterators

`coroutine.wrap` turns a coroutine body into a function that resumes the coroutine on each call and returns yielded values directly. This makes some producer-style iterators concise because state stays in ordinary locals suspended between calls.

```lua
local function values()
    return coroutine.wrap(function()
        coroutine.yield("a")
        coroutine.yield("b")
        coroutine.yield("c")
    end)
end

local next_value = values()
print(next_value())
print(next_value())
```

Wrapped coroutines report errors differently from explicit `resume`, so choose the form that gives the control and diagnostics you need. For simple iteration, closures or a generic-for iterator function may be clearer; use a coroutine when suspension naturally models the producer's state.
