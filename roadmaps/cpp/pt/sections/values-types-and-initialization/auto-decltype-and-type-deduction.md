# `auto`, `decltype` e Dedução de Tipo

`auto` pede ao compilador para deduzir o tipo a partir do initializer usando regras semelhantes às de templates. Referências e top-level const nem sempre são preservados sem sintaxe explícita. `decltype` consulta o tipo de uma expressão com regras próprias.

```cpp
const int count = 42;
auto a = count;          // int
auto &b = count;         // const int&
decltype(count) c = 7;   // const int
```

Dedução é valiosa quando o tipo é óbvio pelo lado direito, muito verboso por templates ou intencionalmente genérico. Evite `auto` quando o tipo exato comunica unidade, ownership ou conversão cara que ficaria escondida.
