# `load`, `loadfile` e Chunks Dinâmicos

`load` compila um chunk a partir de texto ou reader function e retorna uma função executável quando a compilação funciona. `loadfile` faz o mesmo a partir de arquivo. Falha de compilação é retornada como resultado, sem executar automaticamente.

```lua
local fn, err = load("return 20 + 22")

if not fn then
    error(err)
end

print(fn())
```

Dynamic loading serve a configuração, plugins, código gerado e embedding, mas carregar texto não confiável como código concede as capacidades disponíveis no environment. Prefira formatos de dados quando precisa apenas de dados e restrinja o environment quando configuração executável for realmente necessária.
