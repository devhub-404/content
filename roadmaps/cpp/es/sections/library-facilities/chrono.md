# Tiempo con `<chrono>`

`<chrono>` modela durations y time points con unidades en el type system. Distintos clocks sirven a propósitos distintos: `steady_clock` es monotónico y adecuado para medir intervalos, mientras los system clocks se relacionan con tiempo civil.

```cpp
using namespace std::chrono;

auto start = steady_clock::now();
do_work();
auto elapsed = steady_clock::now() - start;

std::cout
    << duration_cast<milliseconds>(elapsed).count()
    << " ms
";
```

Evita guardar elapsed time en un entero sin unidad cuando un duration conserva la unidad. Calendario/timezone es un problema diferente de performance; elige tipos adecuados en vez de mezclar timestamps, fechas y durations.
