# Lua como Lenguaje Embebido

Lua fue diseñado para vivir dentro de una aplicación host. El host crea un Lua state, expone funciones o userdata seleccionados, carga scripts y recibe resultados mediante la C API. Juegos, editores, productos de red y otras aplicaciones pueden usar Lua como capa de scripting o extensión.

```lua
-- The host may expose a small API:
local player = game.current_player()
player:set_score(player:score() + 10)
```

El embedding funciona mejor cuando el host expone una pequeña API de dominio en vez de cada puntero o subsistema interno. Trata la frontera como una interfaz pública: define ownership, errors, lifetime, capacidades permitidas y qué versión de Lua soporta el host.
