# JDK, JVM y Herramientas

El JDK contiene compiler, launcher, JShell, Javadoc, JAR tooling, soporte de debug y runtime. La JVM ejecuta bytecode; el JDK es la distribución de desarrollo que la rodea. Los proyectos modernos suelen usar Maven o Gradle sobre estas herramientas.

```java
// Common commands:
// javac Main.java
// java Main
// jshell
// javadoc ...
// jar ...
```

Entiende `javac`, `java`, classpath, modules y JARs antes de tratar un build tool como magia. Maven/Gradle automatizan el grafo, pero los errores siguen viniendo del mismo modelo de plataforma.
