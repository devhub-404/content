# Tipos Primitivos

Java possui oito tipos primitivos: quatro inteiros, dois floating-point, `char` e `boolean`. Primitivos não são objetos, embora boxing possa envolvê-los em classes como `Integer` quando um objeto é necessário.

```java
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
boolean ready = true;
char letter = 'A';
```

Escolha pelo range e contrato. `int` é o inteiro geral, `long` serve a ranges maiores e floating-point não é aritmética decimal exata para dinheiro.
