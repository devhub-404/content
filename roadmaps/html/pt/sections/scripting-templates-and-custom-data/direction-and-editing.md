# Direção, Ganchos de Foco e Conteúdo Editável

`dir` expressa a direção base do texto e pertence ao HTML quando a direção é conhecida pelo conteúdo. `bdi` pode isolar um trecho cuja direção é desconhecida para que ele não perturbe o texto bidirecional ao redor. Direção é informação semântica; propriedades lógicas de CSS podem adaptar o layout a ela.

```html
<html lang="ar" dir="rtl">

<p>User <bdi>إياد</bdi> scored 12 points.</p>

<div id="error-summary" tabindex="-1">
  Please correct the highlighted fields.
</div>

<div contenteditable="true">Edit this note.</div>
```

`tabindex="-1"` torna um elemento focável por programação sem adicioná-lo à ordem normal do Tab; `0` pode colocar um alvo personalizado adequado na ordem sequencial. Evite valores positivos porque criam uma ordem paralela frágil. `contenteditable` torna conteúdo editável, mas não fornece um editor completo: seleção, colagem, sanitização, desfazer, armazenamento e acessibilidade ainda exigem projeto deliberado.
