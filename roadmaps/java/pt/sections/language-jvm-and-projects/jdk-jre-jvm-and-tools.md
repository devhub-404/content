# JDK, JVM e Ferramentas

O JDK contém compilador, launcher, JShell, Javadoc, JAR tooling, debug support e runtime. A JVM executa bytecode; o JDK é a distribuição de desenvolvimento ao redor dela. Projetos modernos normalmente usam Maven ou Gradle sobre essas ferramentas.

```java
// Common commands:
// javac Main.java
// java Main
// jshell
// javadoc ...
// jar ...
```

Entenda `javac`, `java`, classpath, modules e JARs antes de tratar build tool como mágica. Maven/Gradle automatizam o grafo, mas erros continuam vindo do mesmo modelo de plataforma.
