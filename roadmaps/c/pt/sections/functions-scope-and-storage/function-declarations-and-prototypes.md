# Declarações e Protótipos de Função

Uma declaração de função descreve nome, retorno e tipos de parâmetros. Um protótipo permite ao compilador verificar chamadas antes de ver a definição. C23 remove definições antigas sem protótipo, então código moderno deve usar prototypes corretos.

```c
double area(double radius);

double area(double radius) {
    return 3.141592653589793 * radius * radius;
}
```

Coloque declarações públicas em headers e inclua o próprio header no arquivo que as define. Assim a implementação não diverge silenciosamente da API. Em `f(void)`, `void` significa explicitamente que não há parâmetros.
