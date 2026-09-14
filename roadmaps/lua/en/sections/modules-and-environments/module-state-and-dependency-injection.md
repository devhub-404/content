# Module State and Dependency Injection

Because module chunks run as functions and closures retain upvalues, a module can keep private state without globals. Factory-style modules can also accept dependencies explicitly and return a configured table or closure set.

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

Explicit dependencies are easier to test and reuse than modules that silently read mutable globals. Reserve module-level singletons for state that truly belongs to the process-wide module instance. When multiple independent instances make sense, expose a constructor or factory instead.
