# Reglas CSS y hojas de estilo

CSS es un lenguaje de hojas de estilo. Un selector elige elementos y un bloque de declaraciones asigna valores a propiedades. Una hoja puede contener reglas normales, comentarios y at-rules como `@media`, `@supports` o `@layer`.

```css
p {
  color: navy;
  font-size: 1.1rem;
}
```

Las hojas externas son la opción habitual para estilos reutilizables. Un bloque `<style>` sirve para reglas específicas del documento y el atributo `style` conviene reservarlo para casos dinámicos muy concretos. Mantén el significado del contenido en HTML y usa CSS para la presentación.
