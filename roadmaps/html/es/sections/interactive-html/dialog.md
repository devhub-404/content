# Diálogos

`dialog` representa una caja de diálogo. JavaScript puede abrirla de forma no modal con `show()` o modal con `showModal()`, y los mecanismos declarativos modernos también pueden controlarla. Un diálogo modal entra en la top layer y el navegador gestiona aspectos importantes de foco e inercia del fondo.

```html
<dialog id="confirm-delete">
  <p>Delete this file?</p>
  <form method="dialog">
    <button value="cancel">Cancel</button>
    <button value="delete">Delete</button>
  </form>
</dialog>
```

Un formulario dentro de un dialog puede usar `method="dialog"` para que el submit cierre el diálogo en vez de enviar una petición. Usa el elemento nativo cuando la interfaz sea realmente un diálogo: reproducir correctamente foco, Escape, modalidad y accesibilidad con un `div` genérico es más difícil de lo que parece.
