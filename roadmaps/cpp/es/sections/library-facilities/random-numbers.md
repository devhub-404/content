# Números Aleatorios

La librería `<random>` separa engines, que generan secuencias pseudo-random, de distributions, que transforman la salida en la distribución deseada. Es mucho más expresiva que `rand()`.

```cpp
std::random_device rd;
std::mt19937 engine(rd());

std::uniform_int_distribution<int> die(1, 6);

int roll = die(engine);
```

El seeding depende del caso. Las simulaciones pueden necesitar seeds fijas reproducibles, mientras seguridad exige una fuente criptográficamente adecuada que los engines estándar no prometen. No confundas conveniencia estadística con seguridad criptográfica.
