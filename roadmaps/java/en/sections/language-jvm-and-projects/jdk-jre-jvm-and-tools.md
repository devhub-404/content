# JDK, JVM, and Core Tools

The JDK contains the compiler, launcher, JShell, Javadoc, JAR tooling, debugger support, and the runtime needed to build and run Java programs. The JVM executes bytecode; the JDK is the development distribution around it. Modern projects often use Maven or Gradle on top of the standard tools.

```java
// Common commands:
// javac Main.java
// java Main
// jshell
// javadoc ...
// jar ...
```

Understand `javac`, `java`, classpaths, modules, and JARs before treating a build tool as magic. Build tools automate dependency graphs and conventions, but compiler/runtime errors still come from the same underlying platform model.
