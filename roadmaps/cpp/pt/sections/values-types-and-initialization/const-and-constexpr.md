# `const`, `constexpr` e Avaliação Constante

`const` impede modificação após inicialização por aquela interface, enquanto `constexpr` diz que uma variável ou função pode participar de constant evaluation quando os inputs permitem. C++ moderno consegue executar bastante lógica comum durante compilação.

```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int area = square(6);
const int runtime_value = read_value();
```

Uma função `constexpr` não roda necessariamente em compile time em toda chamada; também pode executar em runtime. Use constant evaluation para valores e validações naturalmente conhecidas na compilação, não para mover trabalho caro sem benefício claro.
