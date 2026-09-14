# Warnings, Sanitizers e Static Analysis

Build de produção deve habilitar warnings fortes e tratar novos warnings inexplicados como defeitos. Sanitizers expõem muitos erros de memória, UB e concorrência; static analyzers podem encontrar caminhos não executados nos testes.

```cpp
// Example build:
// c++ -std=c++23 -Wall -Wextra -Wconversion //     -fsanitize=address,undefined main.cpp
```

Nenhuma ferramenta prova correção. Use múltiplos compiladores quando portabilidade importa, rode sanitizers em CI e combine com testes, review e análise de dependências. Bugs low-level ficam muito mais fáceis quando detectados perto da origem.
