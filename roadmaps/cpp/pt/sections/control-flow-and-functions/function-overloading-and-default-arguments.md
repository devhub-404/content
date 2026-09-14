# Overloading de Funções e Argumentos Default

C++ permite funções com mesmo nome quando overload resolution consegue escolher entre listas de parâmetros distintas. Viabilidade, conversões implícitas, templates e regras de ranking determinam o overload escolhido.

```cpp
void log(int value);
void log(double value);
void log(std::string_view value);

void connect(std::string_view host, int port = 443);
```

Default arguments preenchem argumentos finais omitidos e não são overload separado. Evite sets onde várias opções dependem de conversões surpreendentes. Tipos de domínio fortes e nomes explícitos podem ser mais claros que muitas assinaturas quase iguais.
