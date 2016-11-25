# Buy ticket

This is how you link to the ticket purchase/checkout page. To be used inside a `com_liquid2`

```html
    <a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&amp;{{ currentQueryString }}">Buy ticket</a>
```