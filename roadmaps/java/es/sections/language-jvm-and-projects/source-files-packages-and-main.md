# Source Files, Packages y `main`

Los programas Java tradicionales declaran classes en compilation units y las organizan en packages. Java 25 también hizo permanentes los compact source files e instance `main`, reduciendo ceremonia en programas pequeños sin cambiar el modelo general de classes/packages.

```java
package example.app;

public class Main {
    public static void main(String[] args) {
        System.out.println(args.length);
    }
}
```

Usa formas compactas en ejercicios, scripts y herramientas pequeñas cuando ayuden. En libraries y apps mayores, packages y tipos nombrados siguen siendo esenciales para tooling, modules, testing y diseño de API.
