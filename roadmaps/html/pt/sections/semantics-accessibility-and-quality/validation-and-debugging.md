# Validação e Depuração de HTML

HTML é tolerante a ponto de marcação inválida ainda parecer correta. Validação encontra IDs duplicados, aninhamento inválido, atributos obrigatórios ausentes, construções obsoletas e outros problemas de conformidade antes que se tornem surpresas específicas de navegador. O DevTools mostra o DOM realmente criado pelo parser, que pode diferir do código-fonte após recuperação de erro.

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```

Validação é necessária, mas não suficiente. Um documento pode ser tecnicamente válido e ainda usar texto de link vago, hierarquia ruim de títulos, alt inútil, controles sem label ou o elemento semântico errado. Revise conteúdo real com teclado e ferramentas de acessibilidade e trate erros do validador como defeitos estruturais, não como lint cosmético.
