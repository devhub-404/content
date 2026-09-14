# Pipelines de Stream

Streams descrevem pipelines lazy. Intermediate operations como `filter`/`map` constroem pipeline e terminal operations como `toList`, `reduce` e `count` executam. Stream normalmente é single-use.

```java
List<String> names = users.stream()
    .filter(User::active)
    .map(User::name)
    .sorted()
    .toList();
```

Streams são ótimos para transformações/agregações quando o fluxo fica claro. Não armazenam dados. Loop costuma ser melhor quando control flow, checked exceptions ou side effects complexos dominam.
