# Anchor Positioning

Anchor positioning permite que um elemento posicionado use outro elemento como âncora geométrica. É feito para interfaces como menus, tooltips, callouts e popovers que devem permanecer ligados a um trigger sem cálculos manuais em JavaScript. Funções de âncora também podem referenciar posição ou tamanho do anchor.

```css
.trigger {
  anchor-name: --menu-trigger;
}

.menu {
  position: absolute;
  position-anchor: --menu-trigger;
  position-area: block-end span-inline-end;
}
```

O modelo inclui placements de fallback para o navegador tentar outra posição quando a preferida causaria overflow. Anchor positioning é moderno, então verifique o subconjunto exato suportado pelo baseline de navegadores e preserve fallback utilizável. Ele resolve geometria; não substitui semântica nem comportamento de interação de popover, dialog, menu ou tooltip.
