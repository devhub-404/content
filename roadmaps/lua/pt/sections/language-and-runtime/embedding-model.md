# Lua como Linguagem Embutida

Lua foi projetada para viver dentro de uma aplicação host. O host cria um Lua state, expõe funções ou userdata selecionados, carrega scripts e recebe resultados pela C API. Jogos, editores, produtos de rede e outras aplicações podem usar Lua como camada de scripting ou extensão.

```lua
-- The host may expose a small API:
local player = game.current_player()
player:set_score(player:score() + 10)
```

Embedding funciona melhor quando o host expõe uma API pequena de domínio em vez de cada ponteiro ou subsistema interno. Trate a fronteira como interface pública: defina ownership, errors, lifetime, capacidades permitidas e qual versão de Lua é suportada.
