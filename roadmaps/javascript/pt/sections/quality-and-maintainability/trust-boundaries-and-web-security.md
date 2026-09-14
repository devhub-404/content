# Fronteiras de Confiança e Segurança Web

Parâmetros de URL, respostas de rede, storage, mensagens e input do usuário são dados vindos de fronteiras de confiança, não valores automaticamente válidos. Valide forma e regras de domínio antes de depender deles. No DOM, use APIs de texto para texto e evite inserir strings não confiáveis como HTML.

```js
const item = document.createElement("li");
item.textContent = untrustedName;

const response = await fetch("/api/profile", {
  credentials: "same-origin",
});
```

Conceitos como same-origin policy, CORS, Content Security Policy, cookies, credentials, sandboxing e Trusted Types moldam o que JavaScript pode fazer com segurança. São mecanismos da plataforma, não sintaxe ECMAScript. Não resolva falha de CORS ou CSP enfraquecendo segurança globalmente; identifique a relação de confiança pretendida e conceda a menor permissão necessária.
