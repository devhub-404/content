# `main` and Program Termination

A hosted C program starts at `main`. The portable forms are `int main(void)` and a form that receives command-line arguments, traditionally `int main(int argc, char *argv[])` or an equivalent declaration. Returning from `main` terminates the program similarly to calling `exit` with that status.

```c
#include <stdlib.h>

int main(int argc, char **argv) {
    if (argc < 2) {
        return EXIT_FAILURE;
    }

    return EXIT_SUCCESS;
}
```

Use `EXIT_SUCCESS` and `EXIT_FAILURE` when the exact numeric convention should remain portable, or document a specific exit-code contract for your environment. Do not use `void main`; it is not a standard hosted-program signature. Startup and termination also interact with `atexit` handlers, buffered streams, and implementation-specific process facilities.
