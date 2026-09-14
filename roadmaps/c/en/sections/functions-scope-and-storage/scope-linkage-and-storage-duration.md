# Scope, Linkage, and Storage Duration

Scope answers where a name is visible, linkage answers whether declarations in different places refer to the same entity, and storage duration describes how long an object exists. These are separate concepts even though keywords such as `static` participate in more than one of them.

```c
static int file_counter;

void tick(void) {
    static int calls;
    ++calls;
    ++file_counter;
}
```

A block local normally has automatic storage duration. A file-scope `static` name has internal linkage, while a block-scope `static` object persists for the program's lifetime. Understand each effect instead of translating `static` into one vague idea such as “global”.
