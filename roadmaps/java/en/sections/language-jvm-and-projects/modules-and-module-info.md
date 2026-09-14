# The Java Platform Module System

The module system adds a level above packages. A named module declares required modules, exported packages, services, and other relationships in `module-info.java`. It improves strong encapsulation and reliable dependency configuration for modular applications and libraries.

```java
module example.app {
    requires java.net.http;
    exports example.api;
}
```

Modules are not required for every project. Learn package/classpath development first, then adopt modules when strong boundaries, jlink images, or modular deployment bring concrete value. Avoid exporting implementation packages simply to make reflection or tests easier.
