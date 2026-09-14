# Sequences, Chaves Inteiras e Length

Lua representa arrays convencionalmente como tables com chaves inteiras começando em 1. Uma sequence possui border bem definido para chaves consecutivas, e `#` é confiável para sequences adequadas, não para tables sparse arbitrárias.

```lua
local colors = {"red", "green", "blue"}

print(colors[1])
print(#colors)

colors[#colors + 1] = "gold"
```

Não crie holes e depois presuma que `#` possui uma única resposta óbvia. Use count explícito ou outra representação para dados sparse. Lua 5.5 também fornece `table.create` para pré-alocar capacity quando isso traz benefício medido.
