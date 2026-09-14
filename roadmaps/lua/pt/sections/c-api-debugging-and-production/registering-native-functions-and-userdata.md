# Registrando Functions Nativas e Userdata

Um host pode expor C functions como callables Lua e agrupá-las em libraries. Full userdata armazena memória controlada pelo host dentro do lifetime de Lua, enquanto light userdata é basicamente raw pointer com semântica de ownership muito mais fraca.

```lua
-- After the host registers a library:
local socket = net.connect("example.com", 443)

socket:send("hello")
socket:close()
```

Prefira full userdata com metatables para objetos nativos owning. Valide argumentos, defina close/finalization e nunca presuma que pointer continua válido só porque Lua mantém um valor representando-o. Binding code é trust boundary.
