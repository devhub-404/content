# Depuração de Programas C Nativos

Debuggers nativos permitem breakpoints, inspeção de stack frames e memória, step e análise de crashes/core dumps. Compile com debug information e nível de otimização adequado para que o estado em source seja compreensível.

```c
int divide(int a, int b) {
    return a / b;
}
```

Quando um crash aparece longe da causa, procure corrupção anterior, use-after-free ou aritmética de size inválida. Reproduza com input mínimo, combine debugger e sanitizers e preserve binário/símbolos exatos de produção ao investigar.
