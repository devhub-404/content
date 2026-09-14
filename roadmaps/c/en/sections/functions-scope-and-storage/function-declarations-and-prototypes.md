# Function Declarations and Prototypes

A function declaration describes the function's name, return type, and parameter types. A prototype lets the compiler check calls before seeing the definition. C23 removes old-style unprototyped function definitions from the language, so modern code should always use proper prototypes.

```c
double area(double radius);

double area(double radius) {
    return 3.141592653589793 * radius * radius;
}
```

Place public function declarations in headers and include the header in the implementation file that defines them. This prevents the implementation from silently drifting away from its public declaration. `void` in `f(void)` explicitly means no parameters.
