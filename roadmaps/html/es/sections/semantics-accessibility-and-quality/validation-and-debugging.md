# Validación y depuración de HTML

HTML es tan tolerante que el marcado inválido puede seguir pareciendo correcto. La validación encuentra IDs duplicados, anidamiento inválido, atributos obligatorios ausentes, construcciones obsoletas y otros problemas antes de que se conviertan en sorpresas entre navegadores. DevTools muestra el DOM que el parser realmente creó, que puede diferir del source después de reparar errores.

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```

Validar es necesario, pero no suficiente. Un documento puede ser técnicamente válido y aun tener texto de enlaces vago, jerarquía pobre de encabezados, alt inútil, controles sin label o elementos semánticos equivocados. Revisa contenido real con teclado y herramientas de accesibilidad y trata los errores del validador como defectos estructurales, no como lint cosmético.
