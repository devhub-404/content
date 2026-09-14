# Resolução de Módulos pelo Host

ECMAScript define sintaxe e semântica de linking de módulos, mas o host decide como um module specifier vira código-fonte. Navegadores resolvem principalmente URLs e normalmente exigem specifiers relativos/absolutos resolvíveis salvo import map. Runtimes de servidor e bundlers adicionam regras de resolução de arquivos e pacotes.

```js
import { format } from "./format.js";
import { readFile } from "node:fs/promises";
```

Por isso bare import de pacote pode funcionar em um ambiente e falhar no navegador sem tooling. Extensões, package exports, interoperabilidade CommonJS, aliases e resolução condicional são preocupações do ambiente ao redor do sistema de módulos. Teste pacotes no mesmo runtime e configuração de build usados pelos consumidores.
