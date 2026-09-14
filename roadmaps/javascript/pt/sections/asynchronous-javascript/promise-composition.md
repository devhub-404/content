# Composição de Promises

Combinators de Promise codificam políticas de concorrência. `Promise.all()` exige todos os inputs e rejeita na primeira rejection. `allSettled()` aguarda todos os resultados. `race()` resolve com o primeiro settlement, enquanto `any()` fulfill com o primeiro sucesso e rejeita apenas se todos falharem.

```js
const [user, settings] = await Promise.all([
  loadUser(),
  loadSettings(),
]);

const first = await Promise.any([
  fetchFromPrimary(),
  fetchFromReplica(),
]);
```

Iniciar operações independentes antes de aguardá-las permite concorrência; awaits consecutivos podem serializar trabalho sem intenção. Composição não cancela automaticamente operações perdedoras ou falhas. Cancelamento normalmente vem da API do host—como `AbortController` no Fetch—e precisa ser conectado separadamente quando trabalho abandonado é caro ou produz efeitos colaterais.
