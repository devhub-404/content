# Sincronização, Locks e Atomics

Java Memory Model define visibility/ordering entre threads. `synchronized`, locks, volatile, atomics e concurrent collections estabelecem garantias diferentes. Shared mutable state sem sync pode ter stale reads/races.

```java
private final Object lock = new Object();
private int count;

void increment() {
    synchronized (lock) {
        count++;
    }
}
```

Use a primitive mais simples para a invariante. Mantenha critical sections pequenos, defina lock order e prefira imutabilidade ou ownership transfer quando evita coordenação.
