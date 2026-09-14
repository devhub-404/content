# Overloading de Funciones y Argumentos Default

C++ permite funciones con el mismo nombre cuando overload resolution puede elegir entre listas de parámetros distintas. Viabilidad, conversiones implícitas, templates y reglas de ranking determinan el overload elegido.

```cpp
void log(int value);
void log(double value);
void log(std::string_view value);

void connect(std::string_view host, int port = 443);
```

Los default arguments rellenan argumentos finales omitidos y no son un overload separado. Evita sets donde varias opciones dependan de conversiones sorprendentes. Tipos de dominio fuertes y nombres explícitos pueden ser más claros que muchas firmas casi iguales.
