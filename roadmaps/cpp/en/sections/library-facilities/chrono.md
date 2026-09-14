# Time with `<chrono>`

`<chrono>` models durations and time points with units in the type system. Different clocks serve different purposes: `steady_clock` is monotonic and suitable for measuring intervals, while system-clock facilities relate to civil/calendar time.

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

Avoid storing elapsed time as an unlabelled integer when a duration type can preserve units. Calendar and timezone work is a different problem from measuring performance; choose the appropriate chrono types rather than mixing timestamps, wall-clock dates, and durations.
