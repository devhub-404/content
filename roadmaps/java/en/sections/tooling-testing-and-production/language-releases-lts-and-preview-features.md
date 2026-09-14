# Releases, LTS, and Preview Features

Java has a six-month feature-release cadence and designated LTS releases used by many production organizations. Some language/platform features spend releases in preview before becoming permanent, changing, or being withdrawn.

```java
// Compile a preview experiment only when intended:
// javac --enable-preview --release 25 Example.java
// java --enable-preview Example
```

Do not make preview features a silent dependency in ordinary libraries. Keep the minimum JDK/runtime version explicit, test the versions you claim to support, and distinguish source compatibility, binary compatibility, and runtime deployment requirements.
