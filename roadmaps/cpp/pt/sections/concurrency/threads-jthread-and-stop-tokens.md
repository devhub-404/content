# Threads, `jthread` e Stop Tokens

`std::thread` representa thread e exige join/detach explícito. `std::jthread` faz join automático e integra cancelamento cooperativo por stop tokens, sendo default mais seguro para muitos lifetimes de scope.

```cpp
std::jthread worker([](std::stop_token stop) {
    while (!stop.stop_requested()) {
        do_one_unit();
    }
});
```

Cancelamento é cooperativo: o código precisa checar o token ou usar waits compatíveis. Garanta que dados capturados vivam mais que a thread e prefira abstrações de tasks quando raw threads forem baixo nível demais.
