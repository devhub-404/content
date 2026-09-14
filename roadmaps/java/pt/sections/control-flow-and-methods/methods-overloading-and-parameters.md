# Métodos, Overloading e Parâmetros

Métodos declaram tipos de parâmetros/retorno e Java suporta overloads escolhidos por assinatura e regras de conversão. Java passa argumentos por valor: parâmetros de objeto recebem uma cópia da referência, podendo mutar o objeto mas não rebindar a variável do caller.

```java
static int max(int a, int b) {
    return a >= b ? a : b;
}

static double max(double a, double b) {
    return a >= b ? a : b;
}
```

Mantenha overloads semanticamente consistentes. Java não tem default arguments, então builders, overloads ou config objects são comuns para opções.
