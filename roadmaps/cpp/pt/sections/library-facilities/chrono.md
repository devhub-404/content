# Tempo com `<chrono>`

`<chrono>` modela durations e time points com unidades no type system. Clocks diferentes servem a propósitos diferentes: `steady_clock` é monotônico e bom para medir intervalos, enquanto system clocks relacionam-se a tempo civil.

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

Evite guardar elapsed time em inteiro sem unidade quando duration preserva a unidade. Calendário/timezone é problema diferente de performance; escolha tipos adequados em vez de misturar timestamps, datas e durations.
