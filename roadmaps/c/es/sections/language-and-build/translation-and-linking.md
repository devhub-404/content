# Traducción, Compilación y Enlazado

Un programa C suele dividirse en translation units. El preprocesador trata directivas como `#include`, cada archivo se traduce a código objeto y el linker resuelve símbolos externos para formar un ejecutable o biblioteca. Los errores de compilación, enlazado y runtime pertenecen a etapas distintas.

```c
// math.c
int add(int a, int b) {
    return a + b;
}

// main.c
int add(int, int);

int main(void) {
    return add(2, 3) == 5 ? 0 : 1;
}
```

Las declaraciones permiten describir un símbolo definido en otra translation unit. Las definiciones reservan almacenamiento o aportan cuerpos de función. Coloca declaraciones públicas en headers e incluye ese mismo header tanto en la implementación como en los consumidores para que el compilador compruebe consistencia.
