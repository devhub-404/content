# Modelo de React y Component Tree

React construye interfaces a partir de components: funciones JavaScript que describen cómo debe verse la UI para los inputs actuales. Los components se componen en un árbol y React reconcilia renders posteriores de ese árbol con el entorno host, normalmente el DOM del navegador.

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

Piensa en datos que fluyen por el component tree en vez de editar el DOM manualmente. El render de un component debe describir UI, no ejecutar trabajo ajeno. React puede renderizar más de una vez, interrumpir trabajo o descartar un render antes del commit.
