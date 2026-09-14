# Static Assertions e Attributes

`static_assert` verifica condição constante durante tradução e é útil para assumptions de layout, configuração e plataforma. C23 também padroniza sintaxe de attributes que pode anexar metadata como `[[nodiscard]]`, `[[deprecated]]` e `[[maybe_unused]]` conforme as regras da linguagem.

```c
#include <stdint.h>

static_assert(sizeof(uint32_t) == 4);

[[nodiscard]]
int write_record(const void *data, size_t size);
```

Use assertions de compile time para fatos que o compilador pode provar. Attributes devem comunicar intenção real de API ou otimização e extensões específicas da implementação exigem planejamento de portabilidade.
