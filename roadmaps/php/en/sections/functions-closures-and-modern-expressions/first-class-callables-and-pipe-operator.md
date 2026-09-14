# First-class Callables and the Pipe Operator

First-class callable syntax such as `trim(...)` creates callable values without string-based function names. PHP 8.5 adds the pipe operator `|>`, which feeds the left value into a callable on the right and makes transformation pipelines read left to right.

```php
$slug = ' PHP 8.5 Released '
    |> trim(...)
    |> (fn (string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

Use the pipe operator for linear transformations where each stage takes one input and returns the next value. A long pipeline with hidden side effects or branching can be harder to debug than named intermediate steps.
