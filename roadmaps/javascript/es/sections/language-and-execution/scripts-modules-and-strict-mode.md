# Scripts, módulos y Strict Mode

JavaScript en el navegador puede evaluarse como script clásico o como módulo ECMAScript. Los módulos tienen scope de nivel superior propio, soportan `import` y `export`, permiten `await` en el nivel superior y son strict por defecto. Los scripts clásicos conservan reglas más antiguas de scope y carga.

```html
<script src="/legacy.js" defer></script>
<script type="module" src="/app.js"></script>
```

El código moderno suele beneficiarse de módulos porque las dependencias quedan explícitas y los nombres permanecen locales salvo que se exporten. Strict mode elimina comportamientos heredados propensos a errores. La resolución de módulos depende del host: los navegadores resuelven principalmente URLs y otros runtimes pueden añadir reglas de paquetes.
