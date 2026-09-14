# Arrays e Varargs

Arrays Java são objetos de length fixo com checks de element type em runtime e elementos zero-initialized. Varargs `T...` é implementado como parâmetro array e permite zero ou mais argumentos.

```java
int[] values = {10, 20, 30};

static int sum(int... values) {
    int total = 0;
    for (int value : values) total += value;
    return total;
}
```

Arrays servem a dados fixos e APIs low-level, enquanto collections são mais flexíveis. Generic arrays têm restrições porque arrays são reified em runtime e generics sofrem type erasure.
