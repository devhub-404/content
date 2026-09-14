# Creating and Updating DOM Content

DOM methods can create, insert, move, replace, and remove nodes. `createElement()` creates an HTML element in an HTML document; `textContent` sets text without parsing it as markup; `append`, `prepend`, `before`, `after`, `replaceWith`, and `remove` cover common tree updates.

```js
const item = document.createElement("li");
item.className = "todo";
item.textContent = userInput;

list.append(item);
```

Use text APIs for untrusted text. `innerHTML` intentionally parses markup and is appropriate only when the application owns or safely sanitizes the HTML string. Inserting untrusted strings as HTML can create cross-site scripting vulnerabilities. Prefer building structured nodes or a trusted sanitization strategy rather than escaping markup by hand.
