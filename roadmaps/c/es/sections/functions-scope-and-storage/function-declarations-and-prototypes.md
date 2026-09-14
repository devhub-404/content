# Declaraciones y Prototipos de Función

Una declaración de función describe nombre, retorno y tipos de parámetros. Un prototipo permite al compilador comprobar llamadas antes de ver la definición. C23 elimina las antiguas definiciones sin prototipo, así que el código moderno debe usar prototipos correctos.

```c
double area(double radius);

double area(double radius) {
    return 3.141592653589793 * radius * radius;
}
```

Coloca declaraciones públicas en headers e incluye ese mismo header en el archivo que las define. Así la implementación no se separa silenciosamente de la API. En `f(void)`, `void` significa explícitamente que no hay parámetros.
