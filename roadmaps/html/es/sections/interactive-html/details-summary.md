# `details` y `summary`

`details` crea un control de disclosure y `summary` aporta el control visible que lo abre o cierra. El navegador ya proporciona interacción con puntero y teclado sin JavaScript personalizado. El atributo `open` representa el estado expandido y puede estar presente inicialmente.

```html
<details>
  <summary>Shipping details</summary>
  <p>Orders leave within two business days.</p>
</details>
```

Úsalo para contenido opcional que pueda mostrarse u ocultarse en el mismo lugar. No sustituye a toda interfaz expandible: menús, diálogos modales, pestañas y controles de aplicación tienen modelos de interacción distintos. Empezar por el elemento nativo es valioso porque la semántica y el comportamiento básico ya existen.
