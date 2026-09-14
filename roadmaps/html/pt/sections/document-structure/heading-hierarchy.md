# Hierarquia de Títulos em Documentos Reais

Os títulos de um documento devem formar uma hierarquia legível de `h1` a `h6`. Você não precisa usar todos os níveis em toda página, mas o nível deve refletir o aninhamento. Um título introduz o conteúdo que segue até que outro título de mesmo nível ou superior mude o contexto.

```html
<h1>Developer handbook</h1>

<section>
  <h2>Frontend</h2>
  <section>
    <h3>Accessibility</h3>
    <h4>Keyboard support</h4>
  </section>
</section>
```

Evite escolher níveis pela aparência. Um `h2` pequeno pode ser estilizado com CSS, enquanto um `h5` usado apenas porque parece menor cria uma hierarquia enganosa. Usuários de leitor de tela frequentemente navegam por uma lista de títulos, então uma sequência limpa é navegação prática. Múltiplos `h1` são sintaticamente permitidos no HTML moderno, mas um `h1` claro no nível da página ainda é o padrão de autoria mais simples e interoperável para documentos comuns.
