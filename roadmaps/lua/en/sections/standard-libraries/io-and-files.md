# I/O and Files

The `io` library exposes default input/output streams and file handles. `io.open` returns a file object or an error result, and file methods read, write, seek, flush, and close according to the chosen mode.

```lua
local file <close> = assert(io.open("data.txt", "w"))
file:write("alpha
")
file:write("beta
")
file:flush()
```

Check open and I/O failures instead of assuming filesystem access succeeds. Use to-be-closed locals or explicit close for deterministic resource release. In embedded Lua, the host may omit or replace the I/O library entirely, so portable scripts should know which capabilities their runtime actually provides.
