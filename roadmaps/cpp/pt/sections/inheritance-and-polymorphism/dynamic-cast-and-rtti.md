# RTTI e `dynamic_cast`

RTTI suporta operações como `dynamic_cast` e `typeid` em tipos polimórficos. `dynamic_cast` pode testar e converter com segurança ao longo da hierarquia quando o design realmente precisa descobrir o tipo dinâmico.

```cpp
shape &s = get_shape();

if (auto *c = dynamic_cast<circle *>(&s)) {
    std::cout << c->area() << '
';
}
```

Downcasts frequentes costumam indicar interface base incompleta ou que variant/value model seria mais claro. Use RTTI em fronteiras que realmente exigem type discovery, não como dispatch principal de comportamento comum.
