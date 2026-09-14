# Queries de Preferência do Usuário e Capacidade de Entrada

Media features podem descrever preferências como movimento reduzido, color scheme, contraste e forced colors, além de capacidades de entrada como hover e precisão do ponteiro. Essas features são mais confiáveis do que inferir estilo de interação pela largura do viewport.

```css
@media (prefers-reduced-motion: reduce) {
  .panel { transition: none; }
}

@media (prefers-color-scheme: dark) {
  :root { --surface: #161616; --text: #f5f5f5; }
}

@media (hover: hover) and (pointer: fine) {
  .menu-item:hover { text-decoration: underline; }
}
```

Trate queries de preferência como parte do comportamento normal do produto, não acabamento tardio. Uma tela grande touch pode ter pointer coarse e um dispositivo pequeno pode ter pointer fine, então consulte a capacidade realmente necessária. A experiência padrão deve continuar utilizável quando nenhuma query de melhoria corresponder; hover nunca deve ser o único caminho para informação essencial.
