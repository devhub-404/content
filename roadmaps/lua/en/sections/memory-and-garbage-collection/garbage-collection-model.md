# Garbage Collection Model

Lua automatically reclaims unreachable managed objects. Lua 5.5 continues to support collector modes and changes major collections to run incrementally, reducing the need for one large stop-the-world major collection in the ordinary model.

```lua
local data = {}

for i = 1, 1000 do
    data[i] = {value = i}
end

data = nil
collectgarbage("collect")
```

Do not call full collection routinely without evidence. The collector exposes tuning controls through `collectgarbage`, but application defaults are often good enough. Memory growth is frequently caused by reachable data—caches, globals, closures, registries, or host references—not by the collector forgetting unreachable objects.
