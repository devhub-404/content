# Estado de Module y Dependency Injection

Como los module chunks se ejecutan como functions y las closures retienen upvalues, un module puede mantener estado privado sin globals. Los modules tipo factory también pueden aceptar dependencies explícitamente y devolver una table o conjunto de closures configuradas.

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

Las dependencies explícitas son más fáciles de testear y reutilizar que modules que leen globals mutables silenciosamente. Reserva singletons de module para estado realmente process-wide. Si varias instancias tienen sentido, expón un constructor/factory.
