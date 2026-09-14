# Warnings do Compilador e Sanitizers

Um build sério de C deve habilitar um conjunto forte de warnings e tratar novos warnings como defeitos a investigar. Compiladores diferentes detectam classes diferentes de código suspeito, então builds com mais de um compilador são valiosos.

```c
/* Build example:
   cc -std=c23 -Wall -Wextra -Wconversion       -fsanitize=address,undefined main.c
*/
```

Sanitizers de runtime detectam muitos erros de memória, operações undefined e data races durante testes. Não provam segurança em caminhos não testados, mas transformam bugs silenciosos em falhas acionáveis. Combine com testes e análise estática.
