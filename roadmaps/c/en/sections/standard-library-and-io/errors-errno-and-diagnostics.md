# `errno`, Errors, and Diagnostics

Some C library functions report failure through their return value and provide additional information in `errno`. `errno` is meaningful only when a function's contract says it is set for the failure you observed; reading it after a successful call or without checking the primary result is a common mistake.

```c
#include <errno.h>
#include <stdio.h>

errno = 0;
/* call a function documented to use errno */

if (errno != 0) {
    perror("operation");
}
```

Use `perror` or `strerror` for human diagnostics where appropriate, but design your own library APIs with explicit error returns and documented result states. Error codes should not be confused with process exit codes or signals.
