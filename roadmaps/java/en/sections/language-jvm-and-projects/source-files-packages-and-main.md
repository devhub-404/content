# Source Files, Packages, and `main`

Traditional Java programs declare classes in compilation units and organize them into packages. Java 25 also makes compact source files and instance `main` methods permanent, which reduces ceremony for small programs without changing the broader class/package model.

```java
package example.app;

public class Main {
    public static void main(String[] args) {
        System.out.println(args.length);
    }
}
```

Use compact source forms for exercises, scripts, and small tools when they clarify the example. For libraries and larger applications, explicit packages and named types still create the boundaries needed by tooling, modules, testing, and API design.
