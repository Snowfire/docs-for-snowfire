# Markdown

```html
<sf-markdown id="{{ component_id }}" description="Markdown"></sf-markdown>
```

## Show code blocks with syntax highlight

We support GitHub flavoured code blocks with backticks \`. To make these show up with syntax highlight, add this code to your `head` tag.

```html
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.4.0/styles/default.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.4.0/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
```
