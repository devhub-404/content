# Java Platform Module System

O module system adiciona uma camada acima de packages. Um módulo nomeado declara requirements, exported packages, services e outras relações em `module-info.java`, permitindo strong encapsulation e configuração confiável.

```java
module example.app {
    requires java.net.http;
    exports example.api;
}
```

Modules não são obrigatórios em todo projeto. Aprenda packages/classpath primeiro e adote módulos quando boundaries fortes, jlink ou deploy modular trouxerem valor. Não exporte implementation packages só para facilitar reflection/testes.
