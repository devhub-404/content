# Booleanos, Caracteres y String Literals

C23 incorpora directamente las keywords `bool`, `true` y `false`. Los character constants y string literals siguen reglas de encoding según su prefijo y el character set de ejecución. Una string literal ordinaria es un array de caracteres terminado por un byte cero.

```c
bool ready = true;
char newline = '
';
const char *message = "hello";
```

Un puntero a una string literal debe tratarse como apuntando a datos inmutables; modificarla es undefined behavior. `char` es un tipo entero pequeño y su signedness es implementation-defined, así que usa `signed char`, `unsigned char` o tipos fixed-width cuando el signo o la semántica de byte importen.
