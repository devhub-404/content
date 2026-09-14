# Synchronization, Locks, and Atomics

The Java Memory Model defines visibility and ordering between threads. `synchronized`, explicit locks, volatile variables, atomic classes, and concurrent collections establish different synchronization guarantees. Unsynchronized shared mutable state can have stale reads and races even if tests appear fine.

```java
private final Object lock = new Object();
private int count;

void increment() {
    synchronized (lock) {
        count++;
    }
}
```

Use the simplest primitive that matches the invariant. Keep critical sections small, define lock ordering when several locks can be acquired, and prefer immutable data or ownership transfer when that avoids coordination entirely.
