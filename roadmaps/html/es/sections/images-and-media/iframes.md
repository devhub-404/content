# Iframes y documentos embebidos

`iframe` incorpora otro contexto de navegación dentro de la página. Dale un `title` útil para que el usuario pueda identificarlo antes de entrar. `width` y `height` aportan geometría inicial y los frames fuera de pantalla pueden usar carga diferida.

```html
<iframe
  src="/embedded/map"
  title="Store location map"
  width="640"
  height="400"
  loading="lazy"
  sandbox>
</iframe>
```

El atributo `sandbox` aplica restricciones al contenido embebido y sus tokens pueden devolver capacidades concretas cuando sea necesario. Es una función de seguridad con reglas sutiles, por lo que conviene conceder solo los permisos imprescindibles. Un iframe es más pesado y aislado que un elemento normal: úsalo cuando realmente necesitas otro documento, no como mecanismo genérico de componentes.
