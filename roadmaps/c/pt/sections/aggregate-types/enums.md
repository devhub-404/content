# Enumerações

Um enum introduz constantes inteiras nomeadas e um tipo de enumeração. É útil para estados discretos, flags com representação projetada separadamente e APIs onde nomes simbólicos comunicam mais que inteiros crus.

```c
enum status {
    STATUS_PENDING,
    STATUS_READY,
    STATUS_FAILED
};

enum status state = STATUS_READY;
```

Não presuma que enum impede automaticamente valores inteiros arbitrários vindos de casts, I/O ou dados corrompidos. Valide inteiros externos antes de interpretá-los como estados. C23 amplia recursos de enum, mas APIs portáveis ainda devem documentar o conjunto válido.
