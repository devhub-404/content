# Estado de Module e Dependency Injection

Como module chunks executam como functions e closures retêm upvalues, um module pode manter estado privado sem globals. Modules factory também podem aceitar dependencies explicitamente e retornar table ou conjunto de closures configuradas.

```lua
local function new_service(clock)
    local service = {}

    function service.now()
        return clock()
    end

    return service
end

return new_service
```

Dependencies explícitas são mais testáveis e reutilizáveis que modules lendo globals mutáveis silenciosamente. Reserve singleton de module para estado realmente process-wide. Se múltiplas instâncias fazem sentido, exponha constructor/factory.
