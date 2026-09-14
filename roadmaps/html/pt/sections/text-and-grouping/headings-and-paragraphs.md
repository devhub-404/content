# Títulos e Parágrafos

HTML fornece seis níveis de título: `h1`, `h2`, `h3`, `h4`, `h5` e `h6`. `h1` é o nível mais alto e `h6` o mais baixo. Os níveis expressam hierarquia, não um tamanho de fonte desejado. Um documento normalmente possui um `h1` principal claro, com níveis menores usados conforme o conteúdo fica mais profundamente aninhado.

```html
<h1>Gardening guide</h1>
<p>This guide covers vegetables and herbs.</p>

<h2>Vegetables</h2>
<h3>Tomatoes</h3>
<h4>Feeding tomatoes</h4>

<h2>Herbs</h2>
<h3>Basil</h3>
```

`p` representa um parágrafo de prosa. Use títulos para nomear seções e parágrafos para blocos comuns de texto. Mantenha os níveis de forma lógica: um `h3` normalmente pertence sob um `h2`, e um `h4` sob um `h3`. CSS pode deixar qualquer título maior ou menor, então nunca escolha `h4` apenas porque a aparência padrão do navegador parece adequada.
