# `auto`, `decltype` y Deducción de Tipo

`auto` pide al compilador deducir el tipo a partir del initializer con reglas parecidas a templates. Las referencias y top-level const no siempre se conservan sin sintaxis explícita. `decltype` consulta el tipo de una expresión con reglas propias.

```cpp
const int count = 42;
auto a = count;          // int
auto &b = count;         // const int&
decltype(count) c = 7;   // const int
```

La deducción es valiosa cuando el tipo es obvio por el lado derecho, muy verboso por templates o deliberadamente genérico. Evita `auto` cuando el tipo exacto comunica una unidad, ownership o una conversión costosa que quedaría oculta.
