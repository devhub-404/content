# Warnings del Compilador y Sanitizers

Un build serio de C debe activar un conjunto fuerte de warnings y tratar los nuevos warnings como defectos a investigar. Distintos compiladores detectan clases diferentes de código sospechoso, así que compilar con más de uno aporta valor.

```c
/* Build example:
   cc -std=c23 -Wall -Wextra -Wconversion       -fsanitize=address,undefined main.c
*/
```

Los sanitizers de runtime detectan muchos errores de memoria, operaciones undefined y data races durante tests. No prueban seguridad en rutas no ejecutadas, pero convierten muchos bugs silenciosos en fallos accionables. Combínalos con tests y análisis estático.
