# Source Files, Packages e `main`

Programas Java tradicionais declaram classes em compilation units e organizam-nas em packages. Java 25 também tornou compact source files e instance `main` permanentes, reduzindo cerimônia em programas pequenos sem mudar o modelo geral de classes/packages.

```java
package example.app;

public class Main {
    public static void main(String[] args) {
        System.out.println(args.length);
    }
}
```

Use formas compactas em exercícios, scripts e ferramentas pequenas quando ajudam. Em libraries e apps maiores, packages e tipos nomeados continuam essenciais para tooling, modules, testes e design de API.
