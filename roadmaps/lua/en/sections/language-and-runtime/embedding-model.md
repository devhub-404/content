# Lua as an Embedded Language

Lua was designed to live inside a host application. The host creates a Lua state, exposes selected functions or userdata, loads scripts, and receives results back through the C API. Games, editors, network products, and other applications can therefore use Lua as a scripting or extension layer.

```lua
-- The host may expose a small API:
local player = game.current_player()
player:set_score(player:score() + 10)
```

Embedding works best when the host exposes a small domain API rather than every internal pointer or subsystem. Treat the boundary as a real public interface: define ownership, errors, lifetime, allowed capabilities, and which Lua version the host supports.
