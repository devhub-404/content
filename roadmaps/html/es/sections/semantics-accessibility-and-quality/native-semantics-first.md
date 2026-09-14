# Primero HTML nativo

Los elementos nativos ya aportan semántica y, a menudo, comportamiento. Un botón puede recibir foco, activarse con teclado, deshabilitarse y se expone como botón a tecnologías de asistencia. Un enlace con `href` participa en la navegación y en el comportamiento de enlaces del navegador. Empezar con `div` genéricos obliga a reconstruir contratos que la plataforma ya ofrece.

```html
<button type="button">Save changes</button>

<a href="/account">Open account</a>
```

ARIA puede complementar HTML cuando la semántica nativa no expresa un estado o relación necesarios, pero no añade automáticamente comportamiento de teclado. Prefiere el elemento nativo cuyo contrato encaja con la tarea: botón para una acción, enlace para navegar, encabezado para un título y controles reales de formulario para entrada del usuario.
