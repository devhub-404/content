# Components, JSX e Expressions

JSX é sintaxe para escrever descrições de elementos perto do JavaScript que prepara seus dados. Chaves entram em expressions JavaScript, atributos usam nomes do React como `className`, e um component retorna uma expressão raiz, frequentemente um fragment quando não precisa de wrapper.

```jsx
function Greeting({ name }) {
  const message = `Hello, ${name}`;
  return <h1 className="greeting">{message}</h1>;
}
```

JSX não é template string e não executa statements arbitrários dentro das chaves. Calcule valores antes do JSX retornado ou use expressions como operador condicional e `map`. Mantenha markup semântico porque React não muda as regras de acessibilidade do HTML.
