# Novas Abas, Downloads, E-mail e Telefone

Links podem solicitar comportamentos além da navegação comum. `download` sugere baixar um recurso da mesma origem; `mailto:` entrega um endereço ao cliente de e-mail do usuário; `tel:` pode entregar um número ao software de chamadas. Esses comportamentos dependem do navegador, política de origem, capacidade do dispositivo e configuração do usuário.

```html
<a href="/report.pdf" download>Download report</a>
<a href="mailto:support@example.com">Email support</a>
<a href="tel:+15551234567">Call support</a>
<a href="/help" target="_blank" rel="noopener">Open help in a new tab</a>
```

`target="_blank"` solicita um novo contexto de navegação, normalmente uma nova aba. Abrir abas inesperadamente pode desorientar, então use apenas quando a tarefa se beneficia de manter a página atual. Navegadores modernos protegem novas abas contra vários riscos de opener, mas valores de `rel` ainda comunicam relação e intenção de segurança. O texto visível deve informar qual é o destino ou arquivo.
