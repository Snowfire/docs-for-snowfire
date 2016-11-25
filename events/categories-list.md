# List of categories

```js
{ com_liquid2 (
  id: '1',
  description: 'Events',
  selectablePage: 'false',
  flake: 'events/categories',
  debug: 'true',
  flakeAdmin: 'events',

  code: '
      <h1>Categories</h1>
      <ul>
          {% for categories as category %}
              <li><a href="{{ page.url }}?kategori={{ category.slug }}">{{ category.name }}</a></li>
          {% end_for %}
      </ul>
  '
)}
```