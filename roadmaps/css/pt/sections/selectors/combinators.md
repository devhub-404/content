# Combinadores

Combinadores expressam relações. Um espaço significa descendente, `>` filho direto, `+` irmão imediatamente seguinte e `~` irmãos posteriores com o mesmo pai. Essas relações são poderosas porque permitem ao CSS usar estrutura já presente no documento.

```css
article p { color: #333; }
article > p { max-inline-size: 68ch; }
h2 + p { margin-block-start: 0; }
h2 ~ p { color: #444; }
```

Use a relação mais fraca que expresse a dependência real. `article > p` é adequado quando apenas parágrafos diretos importam, enquanto `article p` também alcança parágrafos aninhados. Evite seletores que codificam um caminho acidental longo no DOM; pequenas mudanças de markup podem quebrá-los mesmo sem mudança no significado do componente.
