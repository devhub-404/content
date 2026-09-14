# Coroutines: Create, Resume, and Yield

Lua coroutines provide cooperative suspension and resumption. A coroutine is a Lua thread object with its own execution stack. `coroutine.resume` continues it, `coroutine.yield` suspends it, and values can travel in both directions across the resume/yield boundary.

```lua
local co = coroutine.create(function()
    for i = 1, 3 do
        coroutine.yield(i)
    end
end)

while coroutine.status(co) ~= "dead" do
    local ok, value = coroutine.resume(co)
    if ok and value then
        print(value)
    end
end
```

Coroutines are not preemptive operating-system threads. Only the running code yields control, which makes them useful for generators, scripted state machines, cooperative schedulers, and async frameworks built by a host. An error inside a resumed coroutine is reported through the resume result rather than thrown directly into the resumer.
