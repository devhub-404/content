# Maven, Gradle, and Dependencies

Maven and Gradle are the dominant build/dependency tools around Java. They compile source sets, resolve transitive dependencies, run tests, package artifacts, and integrate plugins for code generation, analysis, publishing, and application distribution.

```java
// Maven coordinates example:
// groupId: com.example
// artifactId: billing-core
// version: 1.4.0
```

Learn one tool deeply enough to understand dependency scopes, reproducible versions, repositories, and build lifecycle. Dependency upgrades should be reviewed for transitive changes, security, Java-version requirements, and binary/source compatibility.
