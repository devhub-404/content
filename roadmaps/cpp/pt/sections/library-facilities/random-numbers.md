# Random Numbers

A biblioteca `<random>` separa engines, que geram sequências pseudo-random, de distributions, que mapeiam output para a distribuição desejada. É muito mais expressiva que `rand()`.

```cpp
std::random_device rd;
std::mt19937 engine(rd());

std::uniform_int_distribution<int> die(1, 6);

int roll = die(engine);
```

Seeding depende do caso. Simulações podem precisar seeds fixos reproduzíveis, enquanto segurança exige fonte criptograficamente apropriada que os engines padrão não prometem. Não confunda conveniência estatística com segurança criptográfica.
