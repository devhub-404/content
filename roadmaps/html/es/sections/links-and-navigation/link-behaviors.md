# Nuevas pestañas, descargas, correo y teléfono

Los enlaces pueden solicitar comportamientos distintos de la navegación normal. `download` sugiere descargar un recurso; `mailto:` entrega una dirección al cliente de correo; `tel:` puede entregar un número a una aplicación de llamadas. El comportamiento final depende del navegador, el origen, el dispositivo y la configuración del usuario.

```html
<a href="/report.pdf" download>Download report</a>
<a href="mailto:support@example.com">Email support</a>
<a href="tel:+15551234567">Call support</a>
<a href="/help" target="_blank" rel="noopener">Open help in a new tab</a>
```

`target="_blank"` solicita un nuevo contexto de navegación, normalmente una pestaña. Abrir pestañas inesperadamente puede desorientar, así que úsalo cuando conservar la página actual aporte valor. Los valores de `rel` expresan relación y seguridad. El texto visible debe indicar con claridad cuál es el destino o archivo que se abrirá.
