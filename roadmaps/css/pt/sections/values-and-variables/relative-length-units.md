# Unidades Relativas a Fonte, Viewport e Container

Unidades relativas codificam uma relação em vez de tamanho fixo. `em` acompanha o tamanho de fonte local, `rem` a fonte raiz, `ch` e `lh` métricas tipográficas e unidades de viewport acompanham as dimensões do viewport. Variantes modernas `sv*`, `lv*` e `dv*` distinguem estados pequeno, grande e dinâmico do viewport.

```css
.prose { max-inline-size: 68ch; }
.button { padding: .65em 1em; }
.hero { min-block-size: 100svh; }

.card-shell { container-type: inline-size; }
.card h2 { font-size: clamp(1.2rem, 5cqi, 2rem); }
```

Unidades de container como `cqi` e `cqb` acompanham um query container elegível e são úteis para escala local de componentes. Escolha a unidade conforme a relação de design: dimensões ligadas à tipografia devem usar unidades de fonte, geometria ligada à tela pode usar viewport, e componentes reutilizáveis não devem depender do viewport quando a restrição real é o container.
