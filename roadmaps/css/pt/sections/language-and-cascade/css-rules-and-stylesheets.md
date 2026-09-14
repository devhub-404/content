# Regras CSS e Folhas de Estilo

CSS é uma linguagem de folhas de estilo: seletores escolhem elementos e declarações atribuem valores a propriedades. Um bloco de declarações pode conter vários pares propriedade/valor, e uma folha de estilo pode conter regras, comentários e at-rules como `@media`, `@supports` e `@layer`.

```css
p {
  color: navy;
  font-size: 1.1rem;
}
```

Folhas externas são a escolha normal para estilos reutilizáveis do site. Um bloco `<style>` é útil para regras específicas do documento, enquanto atributos inline `style` devem ficar para casos dinâmicos estreitos porque participam da cascata com precedência de autor especialmente forte. Deixe o CSS cuidar da apresentação e o HTML do significado do documento.
