# Referências e Ponteiros

Uma referência é um alias ligado a um objeto/função e não é reseated como ponteiro após inicialização. Um ponteiro é um objeto que guarda valor de ponteiro, pode ser null, reassigned e suporta operações conforme as regras da linguagem.

```cpp
int value = 42;

int &ref = value;
int *ptr = &value;

ref = 50;
*ptr = 60;
```

Use referências para aliases obrigatórios e ponteiros quando optionality, reseating ou semântica de pointer fazem parte da interface. Nem raw pointer nem reference expressam ownership por si só; APIs modernas devem deixar ownership visível por valores ou smart pointers.
