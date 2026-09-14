# To-be-closed Variables and Resource Cleanup

A local variable marked `<close>` is finalized when control leaves its scope, including error paths, according to Lua's to-be-closed rules. Its value must support the `__close` metamethod, and standard file handles participate in this resource-management model.

```lua
local file <close> = assert(io.open("report.txt", "w"))
file:write("hello
")
-- file is closed when the scope ends
```

Use to-be-closed variables for deterministic cleanup of files, locks, transactions, or host resources that should not wait for garbage collection. Keep acquisition and scope close together so the cleanup point is obvious. Garbage collection remains a fallback for memory, not a substitute for timely release of scarce external resources.
