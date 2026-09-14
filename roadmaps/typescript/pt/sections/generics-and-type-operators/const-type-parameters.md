# Const Type Parameters

Um type parameter `const` pede à inferência para preservar mais informação literal de objetos, arrays e primitivos fornecidos diretamente a chamada genérica. Pode reduzir necessidade de callers escreverem `as const` quando API foi projetada em torno de configuração literal.

```ts
function defineRoutes<const T extends readonly string[]>(routes: T) {
  return routes;
}

const routes = defineRoutes(["/", "/users"]);
// inferred as readonly ["/", "/users"]
```

Isso muda comportamento de inferência, não valores de runtime nem o constraint. Se constraint exige array mutável, inferência readonly literal pode fazer fallback ou se comportar diferente do esperado, então use constraints compatíveis com readonly quando API não muta. Const type parameters são melhores em builders/configuração que realmente se beneficiam de literals preservados.
