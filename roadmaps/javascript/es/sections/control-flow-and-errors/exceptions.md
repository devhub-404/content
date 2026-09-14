# Excepciones

`throw` produce una salida abrupta con un valor, aunque lanzar objetos `Error` es la convención porque aportan mensaje, stack e identidad. `try` envuelve código que puede fallar, `catch` trata la excepción y `finally` ejecuta trabajo al abandonar el bloque, incluso después de un return u otro error.

```js
function parseConfig(text) {
  try {
    return JSON.parse(text);
  } catch (error) {
    throw new Error("Invalid configuration", { cause: error });
  } finally {
    console.log("Parse attempt finished");
  }
}
```

Captura un error donde puedas recuperar, añadir contexto, traducirlo a un error de dominio o garantizar cleanup. Evita catches que simplemente ocultan el fallo. `Error` admite `cause` para conservar la causa original y clases de error customizadas pueden ayudar cuando callers necesitan distinguir categorías.
