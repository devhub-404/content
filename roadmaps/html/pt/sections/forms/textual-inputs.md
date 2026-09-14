# Tipos de Input Textuais

O elemento `input` muda de comportamento conforme seu `type`. Tipos textuais comuns incluem `text`, `email`, `password`, `search`, `url` e `tel`. Tipos especializados podem oferecer validação útil do navegador e interfaces de entrada adequadas ao dispositivo, como um teclado focado em e-mail no celular.

```html
<input type="text" name="name">
<input type="email" name="email">
<input type="password" name="password">
<input type="search" name="q">
<input type="url" name="website">
<input type="tel" name="phone">
```

Escolha o tipo que corresponde aos dados, mas não confunda validação do navegador com validação completa da regra de negócio. `email` verifica sintaxe básica; não sabe se a conta existe. `tel` propositalmente não impõe um formato universal porque números de telefone variam no mundo. A validação do servidor continua sendo a autoridade.
