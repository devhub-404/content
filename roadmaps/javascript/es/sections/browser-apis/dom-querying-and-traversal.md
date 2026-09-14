# Consulta y navegación del DOM

El DOM es una API del navegador que representa el documento como objetos. `querySelector()` y `querySelectorAll()` usan selectores CSS y el árbol expone relaciones de padre, hijos y hermanos. Siempre que puedas, consulta desde la raíz estable más cercana en vez de buscar el documento entero.

```js
const form = document.querySelector("#signup");
const fields = form.querySelectorAll("input");

for (const field of fields) {
  console.log(field.name);
}

console.log(form.parentElement);
```

`querySelectorAll()` devuelve una NodeList estática, mientras algunas APIs antiguas devuelven colecciones live. Prefiere referencias directas y estructura semántica a selectores extremadamente frágiles. El DOM no forma parte de ECMAScript puro: otro runtime solo lo tendrá si proporciona una API equivalente.
