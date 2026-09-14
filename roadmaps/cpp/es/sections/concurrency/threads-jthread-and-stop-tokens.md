# Threads, `jthread` y Stop Tokens

`std::thread` representa un thread y exige join/detach explícito. `std::jthread` hace join automático e integra cancelación cooperativa mediante stop tokens, siendo un default más seguro para muchos lifetimes de scope.

```cpp
std::jthread worker([](std::stop_token stop) {
    while (!stop.stop_requested()) {
        do_one_unit();
    }
});
```

La cancelación es cooperativa: el código debe comprobar el token o usar waits compatibles. Garantiza que los datos capturados vivan más que el thread y prefiere abstracciones de tasks cuando raw threads sean demasiado low-level.
