# Java Platform Module System

El module system añade una capa sobre los packages. Un módulo nombrado declara requirements, packages exportados, services y otras relaciones en `module-info.java`, permitiendo strong encapsulation y configuración fiable.

```java
module example.app {
    requires java.net.http;
    exports example.api;
}
```

Los modules no son obligatorios en todo proyecto. Aprende packages/classpath primero y adopta módulos cuando boundaries fuertes, jlink o despliegue modular aporten valor. No exportes implementation packages solo para facilitar reflection/tests.
