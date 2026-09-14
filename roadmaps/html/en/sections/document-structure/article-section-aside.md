# `article`, `section`, and `aside`

`article` represents a self-contained composition such as a post, news story, forum entry, comment, or other independently meaningful item. `section` represents a thematic grouping within a document, usually identified by a heading. A generic styling wrapper is not automatically a section.

```html
<article>
  <h2>Release 4.2 is available</h2>

  <section>
    <h3>Highlights</h3>
    <p>...</p>
  </section>

  <aside>
    <h3>Related links</h3>
    ...
  </aside>
</article>
```

`aside` represents content related to surrounding content but not part of its main flow, such as contextual notes, related resources, or a complementary sidebar. These elements describe relationships in the content, not screen geometry. An aside does not have to appear at the side, and an article does not have to look like a newspaper story.
