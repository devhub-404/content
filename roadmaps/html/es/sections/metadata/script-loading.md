# Carga de scripts

Un script clásico sin atributos de carga puede pausar el parsing del HTML mientras se descarga y ejecuta. `defer` permite que el parsing continúe y ejecuta los scripts diferidos después de analizar el documento, respetando el orden del documento. Suele ser una buena opción para scripts de aplicación colocados en `head`.

```html
<script src="/scripts/app.js" defer></script>
<script type="module" src="/scripts/main.js"></script>
```

Los módulos usan `type="module"` y ya se difieren por defecto. Admiten `import` y `export`. `async` está pensado para scripts independientes que pueden ejecutarse en cuanto estén listos, sin preservar el orden entre ellos. Elige el modo de carga según las dependencias reales en vez de añadir `async` o `defer` mecánicamente.
