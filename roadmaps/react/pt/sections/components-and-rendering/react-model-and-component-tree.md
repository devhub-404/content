# Modelo do React e Component Tree

React constrói interfaces a partir de components: funções JavaScript que descrevem como a UI deve aparecer para os inputs atuais. Components se compõem em uma árvore, e React reconcilia renders posteriores dessa árvore com o ambiente host, normalmente o DOM do navegador.

```jsx
function App() {
  return (
    <main>
      <Header />
      <Profile />
    </main>
  );
}
```

Pense em dados fluindo pela component tree em vez de editar DOM manualmente. O render de um component deve descrever UI, não executar trabalho paralelo. React pode renderizar mais de uma vez, interromper trabalho ou descartar um render antes do commit.
