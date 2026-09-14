# Allocation and Memory-aware Lua

Tables, closures, strings, and userdata have allocation costs, but optimization should start with measurement. Lua 5.5's `table.create` can preallocate expected array and hash capacity, and hosts can install custom allocators through the C API when integration requirements justify it.

```lua
local items = table.create(1000, 0)

for i = 1, 1000 do
    items[i] = i * 2
end
```

Avoid turning ordinary code into allocation micro-management before finding the real hot path. Reusing large buffers, avoiding temporary tables in tight loops, and choosing compact representations can matter, but algorithm choice and host-boundary costs often dominate small syntax-level savings.
