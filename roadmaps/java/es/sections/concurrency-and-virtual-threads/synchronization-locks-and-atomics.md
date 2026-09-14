# Sincronización, Locks y Atomics

Java Memory Model define visibilidad/ordering entre threads. `synchronized`, locks, volatile, atomics y concurrent collections establecen garantías distintas. Shared mutable state sin sync puede tener stale reads/races.

```java
private final Object lock = new Object();
private int count;

void increment() {
    synchronized (lock) {
        count++;
    }
}
```

Usa la primitive más simple para la invariante. Mantén critical sections pequeños, define lock order y prefiere inmutabilidad u ownership transfer cuando evite coordinación.
